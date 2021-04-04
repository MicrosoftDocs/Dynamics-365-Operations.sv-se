---
title: Begränsa betalsätt för returer utan kvitto
description: Det här avsnittet beskriver hur vissa betalningstyper kan begränsas för återbetalning om returer görs utan ett kvitto.
author: rapraj
manager: AnnBe
ms.date: 03/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailTenderTypeTable
audience: Application User
ms.reviewer: josaw
ms.custom: 15831
ms.assetid: 465893a5-6b4f-4c5f-b305-db071df2d33f
ms.search.region: global
ms.search.industry: Retail
ms.author: yabinl
ms.search.validFrom: 2019-02-01
ms.dyn365.ops.version: AX 10.0.0, Retail Feb 2019 update
ms.openlocfilehash: fc087ea24ebbebd5acd1cf37fdfd5c9422d44be8
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5257059"
---
# <a name="restrict-payment-methods-for-returns-without-a-receipt"></a><span data-ttu-id="e879f-103">Begränsa betalsätt för returer utan kvitto</span><span class="sxs-lookup"><span data-stu-id="e879f-103">Restrict payment methods for returns without a receipt</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="e879f-104">Varje betalningstyp som en återförsäljare godtar, måste konfigureras när systemet installeras.</span><span class="sxs-lookup"><span data-stu-id="e879f-104">Each payment type that a retailer accepts must be configured when the system is set up.</span></span> <span data-ttu-id="e879f-105">Det här avsnittet beskriver hur vissa betalningstyper kan begränsas för återbetalning om returer görs utan ett kvitto.</span><span class="sxs-lookup"><span data-stu-id="e879f-105">This topic describes how certain payment types can be restricted for refund if the returns are made without a receipt.</span></span>

## <a name="set-up-payment-methods"></a><span data-ttu-id="e879f-106">Ange betalsätt</span><span class="sxs-lookup"><span data-stu-id="e879f-106">Set up payment methods</span></span>

<span data-ttu-id="e879f-107">Om du vill ställa in betalsätten måste du göra följande.</span><span class="sxs-lookup"><span data-stu-id="e879f-107">To set up payment methods, the following tasks must be completed.</span></span>
1. <span data-ttu-id="e879f-108">Skapa de betalsätt som har godkänts för hela organisationen.</span><span class="sxs-lookup"><span data-stu-id="e879f-108">Create the payment methods that are accepted by the entire organization.</span></span>
2. <span data-ttu-id="e879f-109">Skapa korttyper och kortnummer för hela organisationen.</span><span class="sxs-lookup"><span data-stu-id="e879f-109">Create organization-wide card types and card numbers.</span></span> <span data-ttu-id="e879f-110">Om kreditkort eller betalkort tas emot måste du först skapa ett betalsätt för kort, och sedan skapa korttyper och kortnummer för hela organisationen.</span><span class="sxs-lookup"><span data-stu-id="e879f-110">If credit cards or debit cards are accepted, you must create one payment method for cards, and then create the organization-wide card types and card numbers.</span></span>
3. <span data-ttu-id="e879f-111">Ställ in betalsätt för butiken.</span><span class="sxs-lookup"><span data-stu-id="e879f-111">Set up store payment methods.</span></span> <span data-ttu-id="e879f-112">Associera betalsätten med varje butiker och ange sedan de butiksspecifika inställningarna för varje betalningsmetod.</span><span class="sxs-lookup"><span data-stu-id="e879f-112">Associate payment methods with each store, and then enter the store-specific settings for each payment method.</span></span>
4. <span data-ttu-id="e879f-113">Ställ in kortbetalsätt för butiker.</span><span class="sxs-lookup"><span data-stu-id="e879f-113">Set up card payment methods for stores.</span></span> <span data-ttu-id="e879f-114">Slutför kortinställningarna för alla kortbetalsätt som butiken godtar.</span><span class="sxs-lookup"><span data-stu-id="e879f-114">For any card payment methods that the store accepts, complete the card setup.</span></span>

<span data-ttu-id="e879f-115">![Butiksinställningar](media/NoReceiptReturns1.png "Inställning av butik")</span><span class="sxs-lookup"><span data-stu-id="e879f-115">![Store Setup](media/NoReceiptReturns1.png "Retail Store Setup")</span></span> 


## <a name="restrict-payment-methods-for-returns-without-a-receipt"></a><span data-ttu-id="e879f-116">Begränsa betalsätt för returer utan kvitto</span><span class="sxs-lookup"><span data-stu-id="e879f-116">Restrict payment methods for returns without a receipt</span></span>

<span data-ttu-id="e879f-117">Spara betalningsmetod, för var och en på sidan **Butikshantering** under **Returer utan kvitto** ange **Begränsa betalsätt för returer** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="e879f-117">For each store payment method, on the **Store management** page, under **Non receipt returns**, set **Restrict for refunds without receipt** to **Yes**.</span></span> 

<span data-ttu-id="e879f-118">Standardvärdet för en alternativknapp är **Nej**, vilket innebär att betalsättet är tillåten för återbetalningar.</span><span class="sxs-lookup"><span data-stu-id="e879f-118">The default value of the toggle is **No**, which ensures that the payment method is allowed for refunds.</span></span> 

<span data-ttu-id="e879f-119">När **Begränsa betalsätt för returer** anges till **Ja**, tillåter inte den valda betalsättet för återbetalningar.</span><span class="sxs-lookup"><span data-stu-id="e879f-119">When **Restrict for refunds without receipt** is set to **Yes**, the selected payment method will not be allowed for refunds.</span></span> 

<span data-ttu-id="e879f-120">![Lagra betalningsmetod](media/NoReceiptReturns3.png "Betalningsmetod för butik")</span><span class="sxs-lookup"><span data-stu-id="e879f-120">![Store payment method](media/NoReceiptReturns3.png "Retail Store Payment Method")</span></span> 

> [!NOTE]
> <span data-ttu-id="e879f-121">När kassören väljer ett betalsätt som är begränsad till bidrag utan ett kvitto, visas ett meddelande för att kontrollera godtagbara betalsätt.</span><span class="sxs-lookup"><span data-stu-id="e879f-121">When a cashier selects a payment method that is restricted for refund without a receipt, a message displays to verify the acceptable payment methods.</span></span>

<span data-ttu-id="e879f-122">![Godkända betalsätt](media/NoReceiptReturns4.png "Godkända betalsätt")</span><span class="sxs-lookup"><span data-stu-id="e879f-122">![Acceptable payment methods](media/NoReceiptReturns4.png "Acceptable payment methods")</span></span> 

<span data-ttu-id="e879f-123">Om en transaktion har en retur med kvitto och en retur utan kvitto, upprätthålls begränsningsvillkoren inte eftersom transaktionen kommer att returnera arbetsflödet med ett kvitto.</span><span class="sxs-lookup"><span data-stu-id="e879f-123">If a transaction has both a receipted return and a return without a receipt, the restriction conditions will not be enforced because the transaction will be a return workflow with a receipt.</span></span> 



[!INCLUDE[footer-include](../includes/footer-banner.md)]