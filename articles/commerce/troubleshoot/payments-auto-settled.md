---
title: Betalningar kvittas automatiskt innan order faktureras eller levereras
description: Det här avsnittet innehåller felsökningsvägledning som kan vara till hjälp när en betalning kvittas på Adyen-portalen omedelbart efter en order, trots att försäljningsordern inte har fakturerats eller levererats.
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
ms.openlocfilehash: 788854a3119eb9ffaf839beb93a5bc15cdcd6387
ms.sourcegitcommit: 6c108be3378b365e6ec596a1a8666d59b758db25
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/12/2021
ms.locfileid: "5585537"
---
# <a name="payments-are-automatically-settled-before-orders-are-invoiced-or-shipped"></a><span data-ttu-id="938a9-103">Betalningar kvittas automatiskt innan order faktureras eller levereras</span><span class="sxs-lookup"><span data-stu-id="938a9-103">Payments are automatically settled before orders are invoiced or shipped</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="938a9-104">Det här avsnittet innehåller felsökningsvägledning som kan vara till hjälp när en betalning kvittas på Adyen-portalen omedelbart efter en order, trots att försäljningsordern inte har fakturerats eller levererats.</span><span class="sxs-lookup"><span data-stu-id="938a9-104">This topic provides troubleshooting guidance that can help when a payment is settled in the Adyen portal immediately after an order is placed, even though the sales order hasn't been invoiced or shipped.</span></span>

## <a name="description"></a><span data-ttu-id="938a9-105">beskrivning</span><span class="sxs-lookup"><span data-stu-id="938a9-105">Description</span></span>

<span data-ttu-id="938a9-106">Efter att en beställning har gjorts avvecklas betalningen omedelbart i Adyen-portalen, även om försäljningsordern inte har fakturerats eller skickats.</span><span class="sxs-lookup"><span data-stu-id="938a9-106">After an order is placed, the payment is immediately settled in the Adyen portal, even though the sales order hasn't been invoiced or shipped.</span></span>

## <a name="resolution"></a><span data-ttu-id="938a9-107">Upplösning</span><span class="sxs-lookup"><span data-stu-id="938a9-107">Resolution</span></span>

### <a name="configure-manual-capture-for-e-commerce-payments-in-the-adyen-portal"></a><span data-ttu-id="938a9-108">Konfigurera manuella insamling för e-handelsbetalningar i Adyen-portalen</span><span class="sxs-lookup"><span data-stu-id="938a9-108">Configure manual capture for e-commerce payments in the Adyen portal</span></span>

<span data-ttu-id="938a9-109">Konfigurera manuella insamling för e-handelsbetalningar i Adyen-portalen med dessa steg.</span><span class="sxs-lookup"><span data-stu-id="938a9-109">To configure manual capture for e-commerce payments in the Adyen portal, follow these steps.</span></span>

1. <span data-ttu-id="938a9-110">Logga in på Adyen-portal.</span><span class="sxs-lookup"><span data-stu-id="938a9-110">Sign in to the Adyen portal.</span></span>
1. <span data-ttu-id="938a9-111">Välj ditt butikskonto för e-handelskanal i övre högra hörnet.</span><span class="sxs-lookup"><span data-stu-id="938a9-111">In the upper-right corner, select your merchant account for the e-commerce channel.</span></span>
1. <span data-ttu-id="938a9-112">Välj **Konto** i det övre navigeringsfältet och välj **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="938a9-112">On the top navigation, select **Account**, and then select **Settings**.</span></span>
1. <span data-ttu-id="938a9-113">I fältet **Insamlingsfördröjning** välj **manuell**.</span><span class="sxs-lookup"><span data-stu-id="938a9-113">In the **Capture Delay** field, select **manual**.</span></span>

    ![Inställning för insamlingsfördröjning i Adyen-portalen](media/adyen-capture-delay.jpg)

## <a name="additional-resources"></a><span data-ttu-id="938a9-115">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="938a9-115">Additional resources</span></span>

[<span data-ttu-id="938a9-116">Adyen-betalningsinsamling</span><span class="sxs-lookup"><span data-stu-id="938a9-116">Adyen payment capture</span></span>](https://docs.adyen.com/point-of-sale/capturing-payments)

[<span data-ttu-id="938a9-117">Dynamics 365-betalningskoppling för Adyen</span><span class="sxs-lookup"><span data-stu-id="938a9-117">Dynamics 365 Payment Connector for Adyen</span></span>](../dev-itpro/adyen-connector.md)

[<span data-ttu-id="938a9-118">Ställ in Adyen betalningskoppling för Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="938a9-118">Set up the Adyen payment connector for Dynamics 365</span></span>](https://docs.adyen.com/plugins/microsoft-dynamics)
