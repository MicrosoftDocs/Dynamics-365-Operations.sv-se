---
title: Spara för min nästa betalningsalternativ visas inte
description: Det här avsnittet innehåller felsökningsvägledning som kan vara till hjälp när kryssrutan Spara för nästa betalning inte visas under Betalningsmetod på en e-handelsplatss utcheckningssida.
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
ms.openlocfilehash: 3a4fbcd522651ed1b82b72b751ff6ead44c94a71
ms.sourcegitcommit: 6c108be3378b365e6ec596a1a8666d59b758db25
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/12/2021
ms.locfileid: "5585539"
---
# <a name="save-for-my-next-payment-option-doesnt-appear"></a><span data-ttu-id="baf4f-103">Spara för min nästa betalningsalternativ visas inte</span><span class="sxs-lookup"><span data-stu-id="baf4f-103">"Save for my next payment" option doesn't appear</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="baf4f-104">Det här avsnittet innehåller felsökningsvägledning som kan vara till hjälp när kryssrutan **Spara för nästa betalning** inte visas under **Betalningsmetod** på en e-handelsplatss utcheckningssida.</span><span class="sxs-lookup"><span data-stu-id="baf4f-104">This topic provides troubleshooting guidance that can help when the **Save for my next payment** check box doesn't appear under **Payment method** on an e-commerce site's checkout page.</span></span>

## <a name="description"></a><span data-ttu-id="baf4f-105">beskrivning</span><span class="sxs-lookup"><span data-stu-id="baf4f-105">Description</span></span>

<span data-ttu-id="baf4f-106">Kryssrutan **Spara för nästa betalning** visas inte i avsnittet **Betalningsmetod** på en e-handelsplats utcheckningssida.</span><span class="sxs-lookup"><span data-stu-id="baf4f-106">The **Save for my next payment** check box doesn't appear in the **Payment method** section on an e-commerce site's checkout page.</span></span>

<span data-ttu-id="baf4f-107">Följande illustration visar ett exempel på en kassasida som innehåller kryssrutan **Spara för nästa betalning**.</span><span class="sxs-lookup"><span data-stu-id="baf4f-107">The following illustration shows an example of a checkout page that includes the **Save for my next payment** check box.</span></span>

![Spara nästa betalningskryssruta i modulen Betalning](media/payment-module-save-payment.jpg)

## <a name="resolution"></a><span data-ttu-id="baf4f-109">Upplösning</span><span class="sxs-lookup"><span data-stu-id="baf4f-109">Resolution</span></span>

### <a name="verify-that-the-dynamics-365-payment-connector-for-adyen-is-correctly-configured-in-commerce-headquarters"></a><span data-ttu-id="baf4f-110">Kontrollera att Dynamics 365 Payment Connector för Adyen är korrekt konfigurerat i Commerce-administration</span><span class="sxs-lookup"><span data-stu-id="baf4f-110">Verify that the Dynamics 365 Payment Connector for Adyen is correctly configured in Commerce headquarters</span></span>

<span data-ttu-id="baf4f-111">Kontrollera att Dynamics 365 Payment Connector för Adyen är korrekt konfigurerat i Commerce-administration med stegen.</span><span class="sxs-lookup"><span data-stu-id="baf4f-111">To verify that the Dynamics 365 Payment Connector for Adyen is correctly configured in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="baf4f-112">Gå till **Retail och Commerce \> Kanaler \> Onlinebutiker**.</span><span class="sxs-lookup"><span data-stu-id="baf4f-112">Go to **Retail and Commerce \> Channels \> Online Stores**.</span></span>
1. <span data-ttu-id="baf4f-113">Välj onlinebutik.</span><span class="sxs-lookup"><span data-stu-id="baf4f-113">Select the online store.</span></span>
1. <span data-ttu-id="baf4f-114">Kontrollera att snabbflikarna **Betalningskonton** se till att fältet **Tillåt att spara betalningsinformation i näthandel** ange till **True**.</span><span class="sxs-lookup"><span data-stu-id="baf4f-114">On the **Payment accounts** FastTab, make sure that the **Allow saving payment information in e-commerce** field is set to **True**.</span></span>

![Tillåt att betalningsinformation sparas i fältet e-handel i Commerce-administration](media/payment-connector-save-payment.jpg)

## <a name="additional-resources"></a><span data-ttu-id="baf4f-116">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="baf4f-116">Additional resources</span></span>

[<span data-ttu-id="baf4f-117">Betalningsmodul</span><span class="sxs-lookup"><span data-stu-id="baf4f-117">Payment module</span></span>](../payment-module.md)

[<span data-ttu-id="baf4f-118">Spara betalningsinstrument online med anslutningsprogrammet Adyen</span><span class="sxs-lookup"><span data-stu-id="baf4f-118">Saving online payment instruments with the Adyen connector</span></span>](../dev-itpro/adyen-connector-listPI.md)
