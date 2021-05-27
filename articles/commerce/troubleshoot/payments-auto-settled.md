---
title: Betalningar kvittas automatiskt innan order faktureras eller levereras
description: Det här avsnittet innehåller felsökningsvägledning som kan vara till hjälp när en betalning kvittas på Adyen-portalen omedelbart efter en order, trots att försäljningsordern inte har fakturerats eller levererats.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
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
ms.openlocfilehash: b4fd37a3c45f2559c9659f072ca0b6f02e712f53
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6018270"
---
# <a name="payments-are-automatically-settled-before-orders-are-invoiced-or-shipped"></a><span data-ttu-id="b9851-103">Betalningar kvittas automatiskt innan order faktureras eller levereras</span><span class="sxs-lookup"><span data-stu-id="b9851-103">Payments are automatically settled before orders are invoiced or shipped</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b9851-104">Det här avsnittet innehåller felsökningsvägledning som kan vara till hjälp när en betalning kvittas på Adyen-portalen omedelbart efter en order, trots att försäljningsordern inte har fakturerats eller levererats.</span><span class="sxs-lookup"><span data-stu-id="b9851-104">This topic provides troubleshooting guidance that can help when a payment is settled in the Adyen portal immediately after an order is placed, even though the sales order hasn't been invoiced or shipped.</span></span>

## <a name="description"></a><span data-ttu-id="b9851-105">beskrivning</span><span class="sxs-lookup"><span data-stu-id="b9851-105">Description</span></span>

<span data-ttu-id="b9851-106">Efter att en beställning har gjorts avvecklas betalningen omedelbart i Adyen-portalen, även om försäljningsordern inte har fakturerats eller skickats.</span><span class="sxs-lookup"><span data-stu-id="b9851-106">After an order is placed, the payment is immediately settled in the Adyen portal, even though the sales order hasn't been invoiced or shipped.</span></span>

## <a name="resolution"></a><span data-ttu-id="b9851-107">Upplösning</span><span class="sxs-lookup"><span data-stu-id="b9851-107">Resolution</span></span>

### <a name="configure-manual-capture-for-e-commerce-payments-in-the-adyen-portal"></a><span data-ttu-id="b9851-108">Konfigurera manuella insamling för e-handelsbetalningar i Adyen-portalen</span><span class="sxs-lookup"><span data-stu-id="b9851-108">Configure manual capture for e-commerce payments in the Adyen portal</span></span>

<span data-ttu-id="b9851-109">Konfigurera manuella insamling för e-handelsbetalningar i Adyen-portalen med dessa steg.</span><span class="sxs-lookup"><span data-stu-id="b9851-109">To configure manual capture for e-commerce payments in the Adyen portal, follow these steps.</span></span>

1. <span data-ttu-id="b9851-110">Logga in på Adyen-portal.</span><span class="sxs-lookup"><span data-stu-id="b9851-110">Sign in to the Adyen portal.</span></span>
1. <span data-ttu-id="b9851-111">Välj ditt butikskonto för e-handelskanal i övre högra hörnet.</span><span class="sxs-lookup"><span data-stu-id="b9851-111">In the upper-right corner, select your merchant account for the e-commerce channel.</span></span>
1. <span data-ttu-id="b9851-112">Välj **Konto** i det övre navigeringsfältet och välj **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="b9851-112">On the top navigation, select **Account**, and then select **Settings**.</span></span>
1. <span data-ttu-id="b9851-113">I fältet **Insamlingsfördröjning** välj **manuell**.</span><span class="sxs-lookup"><span data-stu-id="b9851-113">In the **Capture Delay** field, select **manual**.</span></span>

    ![Inställning för insamlingsfördröjning i Adyen-portalen](media/adyen-capture-delay.jpg)

## <a name="additional-resources"></a><span data-ttu-id="b9851-115">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="b9851-115">Additional resources</span></span>

[<span data-ttu-id="b9851-116">Adyen-betalningsinsamling</span><span class="sxs-lookup"><span data-stu-id="b9851-116">Adyen payment capture</span></span>](https://docs.adyen.com/point-of-sale/capturing-payments)

[<span data-ttu-id="b9851-117">Dynamics 365-betalningskoppling för Adyen</span><span class="sxs-lookup"><span data-stu-id="b9851-117">Dynamics 365 Payment Connector for Adyen</span></span>](../dev-itpro/adyen-connector.md)

[<span data-ttu-id="b9851-118">Ställ in Adyen betalningskoppling för Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="b9851-118">Set up the Adyen payment connector for Dynamics 365</span></span>](https://docs.adyen.com/plugins/microsoft-dynamics)
