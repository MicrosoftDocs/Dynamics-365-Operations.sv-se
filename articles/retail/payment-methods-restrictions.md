---
title: Begränsa betalningsmetoder för returer utan kvitto
description: Det här avsnittet beskriver hur vissa betalningstyper kan begränsas för återbetalning om returer görs utan ett kvitto.
author: rapraj
manager: AnnBe
ms.date: 013/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailTenderTypeTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 15831
ms.assetid: 465893a5-6b4f-4c5f-b305-db071df2d33f
ms.search.region: global
ms.search.industry: Retail
ms.author: yabinl
ms.search.validFrom: 2019-02-01
ms.dyn365.ops.version: AX 10.0.0, Retail Feb 2019 update
ms.openlocfilehash: 6e2c32aae06ce7bbdde30809d7a197f43b856af1
ms.sourcegitcommit: bacec397ee48ac583596be156c87ead474ee07df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/05/2019
ms.locfileid: "777187"
---
# <a name="restrict-payment-methods-for-returns-without-a-receipt"></a><span data-ttu-id="befe3-103">Begränsa betalningsmetoder för returer utan kvitto</span><span class="sxs-lookup"><span data-stu-id="befe3-103">Restrict payment methods for returns without a receipt</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="befe3-104">Varje betalningstyp som en återförsäljare godtar, måste konfigureras när systemet installeras.</span><span class="sxs-lookup"><span data-stu-id="befe3-104">Each payment type that a retailer accepts must be configured when the system is set up.</span></span> <span data-ttu-id="befe3-105">Det här avsnittet beskriver hur vissa betalningstyper kan begränsas för återbetalning om returer görs utan ett kvitto.</span><span class="sxs-lookup"><span data-stu-id="befe3-105">This topic describes how certain payment types can be restricted for refund if the returns are made without a receipt.</span></span>

## <a name="set-up-payment-methods"></a><span data-ttu-id="befe3-106">Ange betalningsmetoder</span><span class="sxs-lookup"><span data-stu-id="befe3-106">Set up payment methods</span></span>

<span data-ttu-id="befe3-107">Om du vill ställa in betalsätten måste du göra följande.</span><span class="sxs-lookup"><span data-stu-id="befe3-107">To set up payment methods, the following tasks must be completed.</span></span>
1. <span data-ttu-id="befe3-108">Skapa de betalningsmetoder som har godkänts för hela organisationen.</span><span class="sxs-lookup"><span data-stu-id="befe3-108">Create the payment methods that are accepted by the entire organization.</span></span>
2. <span data-ttu-id="befe3-109">Skapa korttyper och kortnummer för hela organisationen.</span><span class="sxs-lookup"><span data-stu-id="befe3-109">Create organization-wide card types and card numbers.</span></span> <span data-ttu-id="befe3-110">Om kreditkort eller betalkort tas emot måste du först skapa en betalningsmetod för kort, och sedan skapa korttyper och kortnummer för hela organisationen.</span><span class="sxs-lookup"><span data-stu-id="befe3-110">If credit cards or debit cards are accepted, you must create one payment method for cards, and then create the organization-wide card types and card numbers.</span></span>
3. <span data-ttu-id="befe3-111">Ställ in betalningsmetoder för butiken.</span><span class="sxs-lookup"><span data-stu-id="befe3-111">Set up store payment methods.</span></span> <span data-ttu-id="befe3-112">Associera betalningsmetoderna med varje butiker och ange sedan de butiksspecifika inställningarna för varje betalningsmetod.</span><span class="sxs-lookup"><span data-stu-id="befe3-112">Associate payment methods with each store, and then enter the store-specific settings for each payment method.</span></span>
4. <span data-ttu-id="befe3-113">Ställ in kortbetalningsmetoder för butiker.</span><span class="sxs-lookup"><span data-stu-id="befe3-113">Set up card payment methods for stores.</span></span> <span data-ttu-id="befe3-114">Slutför kortinställningarna för alla kortbetalningsmetoder som butiken godtar.</span><span class="sxs-lookup"><span data-stu-id="befe3-114">For any card payment methods that the store accepts, complete the card setup.</span></span>

<span data-ttu-id="befe3-115">![Butiksinställningar](media/NoReceiptReturns1.png "Butiksinställningar")</span><span class="sxs-lookup"><span data-stu-id="befe3-115">![Retail Store Setup](media/NoReceiptReturns1.png "Retail Store Setup")</span></span> 


## <a name="restrict-payment-methods-for-returns-without-a-receipt"></a><span data-ttu-id="befe3-116">Begränsa betalningsmetoder för returer utan kvitto</span><span class="sxs-lookup"><span data-stu-id="befe3-116">Restrict payment methods for returns without a receipt</span></span>

<span data-ttu-id="befe3-117">Spara betalningsmetod, för var och en på sidan **Butikshantering** under **Returer utan kvitto** ange **Begränsa betalningsmetoder för returer** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="befe3-117">For each store payment method, on the **Retail store management** page, under **Non receipt returns**, set **Restrict for refunds without receipt** to **Yes**.</span></span> 

<span data-ttu-id="befe3-118">Standardvärdet för en alternativknapp är **Nej**, vilket innebär att betalningsmetoden är tillåten för återbetalningar.</span><span class="sxs-lookup"><span data-stu-id="befe3-118">The default value of the toggle is **No**, which ensures that the payment method is allowed for refunds.</span></span> 

<span data-ttu-id="befe3-119">När **Begränsa betalningsmetoder för returer** anges till **Ja**, tillåter inte den valda betalningsmetoden för återbetalningar.</span><span class="sxs-lookup"><span data-stu-id="befe3-119">When **Restrict for refunds without receipt** is set to **Yes**, the selected payment method will not be allowed for refunds.</span></span> 

<span data-ttu-id="befe3-120">![Betalningsmetod för butik](media/NoReceiptReturns3.png "Betalningsmetod för butik")</span><span class="sxs-lookup"><span data-stu-id="befe3-120">![Retail Store payment method](media/NoReceiptReturns3.png "Retail Store Payment Method")</span></span> 

> [!NOTE]
> <span data-ttu-id="befe3-121">När kassören väljer en betalningsmetod som är begränsad till bidrag utan ett kvitto, visas ett meddelande för att kontrollera godtagbara betalningsmetoder.</span><span class="sxs-lookup"><span data-stu-id="befe3-121">When a cashier selects a payment method that is restricted for refund without a receipt, a message displays to verify the acceptable payment methods.</span></span>

<span data-ttu-id="befe3-122">![Godtagbara betalningsmetoder](media/NoReceiptReturns4.png "Godtagbara betalningsmetoder")</span><span class="sxs-lookup"><span data-stu-id="befe3-122">![Acceptable payment methods](media/NoReceiptReturns4.png "Acceptable payment methods")</span></span> 

<span data-ttu-id="befe3-123">Om en transaktion har en retur med kvitto och en retur utan kvitto, upprätthålls begränsningsvillkoren inte eftersom transaktionen kommer att returnera arbetsflödet med ett kvitto.</span><span class="sxs-lookup"><span data-stu-id="befe3-123">If a transaction has both a receipted return and a return without a receipt, the restriction conditions will not be enforced because the transaction will be a return workflow with a receipt.</span></span> 

