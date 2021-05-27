---
title: Spara för min nästa betalningsalternativ visas inte
description: Det här avsnittet innehåller felsökningsvägledning som kan vara till hjälp när kryssrutan Spara för nästa betalning inte visas under Betalningsmetod på en e-handelsplatss utcheckningssida.
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
ms.openlocfilehash: af19a3abd78d543d82f7a8d017e2dc413115a6d8
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6018444"
---
# <a name="save-for-my-next-payment-option-doesnt-appear"></a><span data-ttu-id="6ef49-103">Spara för min nästa betalningsalternativ visas inte</span><span class="sxs-lookup"><span data-stu-id="6ef49-103">"Save for my next payment" option doesn't appear</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="6ef49-104">Det här avsnittet innehåller felsökningsvägledning som kan vara till hjälp när kryssrutan **Spara för nästa betalning** inte visas under **Betalningsmetod** på en e-handelsplatss utcheckningssida.</span><span class="sxs-lookup"><span data-stu-id="6ef49-104">This topic provides troubleshooting guidance that can help when the **Save for my next payment** check box doesn't appear under **Payment method** on an e-commerce site's checkout page.</span></span>

## <a name="description"></a><span data-ttu-id="6ef49-105">beskrivning</span><span class="sxs-lookup"><span data-stu-id="6ef49-105">Description</span></span>

<span data-ttu-id="6ef49-106">Kryssrutan **Spara för nästa betalning** visas inte i avsnittet **Betalningsmetod** på en e-handelsplats utcheckningssida.</span><span class="sxs-lookup"><span data-stu-id="6ef49-106">The **Save for my next payment** check box doesn't appear in the **Payment method** section on an e-commerce site's checkout page.</span></span>

<span data-ttu-id="6ef49-107">Följande illustration visar ett exempel på en kassasida som innehåller kryssrutan **Spara för nästa betalning**.</span><span class="sxs-lookup"><span data-stu-id="6ef49-107">The following illustration shows an example of a checkout page that includes the **Save for my next payment** check box.</span></span>

![Spara nästa betalningskryssruta i modulen Betalning](media/payment-module-save-payment.jpg)

## <a name="resolution"></a><span data-ttu-id="6ef49-109">Upplösning</span><span class="sxs-lookup"><span data-stu-id="6ef49-109">Resolution</span></span>

### <a name="verify-that-the-dynamics-365-payment-connector-for-adyen-is-correctly-configured-in-commerce-headquarters"></a><span data-ttu-id="6ef49-110">Kontrollera att Dynamics 365 Payment Connector för Adyen är korrekt konfigurerat i Commerce-administration</span><span class="sxs-lookup"><span data-stu-id="6ef49-110">Verify that the Dynamics 365 Payment Connector for Adyen is correctly configured in Commerce headquarters</span></span>

<span data-ttu-id="6ef49-111">Kontrollera att Dynamics 365 Payment Connector för Adyen är korrekt konfigurerat i Commerce-administration med stegen.</span><span class="sxs-lookup"><span data-stu-id="6ef49-111">To verify that the Dynamics 365 Payment Connector for Adyen is correctly configured in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="6ef49-112">Gå till **Retail och Commerce \> Kanaler \> Onlinebutiker**.</span><span class="sxs-lookup"><span data-stu-id="6ef49-112">Go to **Retail and Commerce \> Channels \> Online Stores**.</span></span>
1. <span data-ttu-id="6ef49-113">Välj onlinebutik.</span><span class="sxs-lookup"><span data-stu-id="6ef49-113">Select the online store.</span></span>
1. <span data-ttu-id="6ef49-114">Kontrollera att snabbflikarna **Betalningskonton** se till att fältet **Tillåt att spara betalningsinformation i näthandel** ange till **True**.</span><span class="sxs-lookup"><span data-stu-id="6ef49-114">On the **Payment accounts** FastTab, make sure that the **Allow saving payment information in e-commerce** field is set to **True**.</span></span>

![Tillåt att betalningsinformation sparas i fältet e-handel i Commerce-administration](media/payment-connector-save-payment.jpg)

## <a name="additional-resources"></a><span data-ttu-id="6ef49-116">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="6ef49-116">Additional resources</span></span>

[<span data-ttu-id="6ef49-117">Betalningsmodul</span><span class="sxs-lookup"><span data-stu-id="6ef49-117">Payment module</span></span>](../payment-module.md)

[<span data-ttu-id="6ef49-118">Spara betalningsinstrument online med anslutningsprogrammet Adyen</span><span class="sxs-lookup"><span data-stu-id="6ef49-118">Saving online payment instruments with the Adyen connector</span></span>](../dev-itpro/adyen-connector-listPI.md)
