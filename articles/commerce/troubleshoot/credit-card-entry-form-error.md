---
title: På en inmatningssida för kreditkort visas ett fel i kassan.
description: Det här avsnittet innehåller felsökningsvägledning som kan vara till hjälp när betalningsmetodavsnittet läses in och visar ett felmeddelande.
author: Reza-Assadi
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
ms.openlocfilehash: d2c5f01d17df79c9b23fd513aaeb5c0605d657e9
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5801781"
---
# <a name="credit-card-entry-page-shows-an-error-at-checkout"></a><span data-ttu-id="ff3e6-103">På en inmatningssida för kreditkort visas ett fel i kassan.</span><span class="sxs-lookup"><span data-stu-id="ff3e6-103">Credit card entry page shows an error at checkout</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ff3e6-104">Det här avsnittet innehåller felsökningsvägledning som kan vara till hjälp när avsnittet **betalningsmetod** läses in och visar ett felmeddelande.</span><span class="sxs-lookup"><span data-stu-id="ff3e6-104">This topic provides troubleshooting guidance that can help when the **Payment method** section isn't loaded and shows an error message.</span></span>

## <a name="description"></a><span data-ttu-id="ff3e6-105">beskrivning</span><span class="sxs-lookup"><span data-stu-id="ff3e6-105">Description</span></span>

<span data-ttu-id="ff3e6-106">När du öppnar utcheckningssidan för en onlinebutik läses avsnittet **Betalningsmetod** in och följande felmeddelande visas: "Något gick fel.</span><span class="sxs-lookup"><span data-stu-id="ff3e6-106">When you open the checkout page of an online store, the **Payment method** section isn't loaded, and the following error message is shown: "Something went wrong.</span></span> <span data-ttu-id="ff3e6-107">Försök igen senare."</span><span class="sxs-lookup"><span data-stu-id="ff3e6-107">Please try again later."</span></span>

![Betalningsmodulfel](media/payment-module-error.jpg)

## <a name="resolution"></a><span data-ttu-id="ff3e6-109">Upplösning</span><span class="sxs-lookup"><span data-stu-id="ff3e6-109">Resolution</span></span>

### <a name="wait-for-the-commerce-scale-unit-cache-to-expire"></a><span data-ttu-id="ff3e6-110">Vänta tills Commerce Scale Unit cache upphöra att gälla</span><span class="sxs-lookup"><span data-stu-id="ff3e6-110">Wait for the Commerce Scale Unit cache to expire</span></span>

<span data-ttu-id="ff3e6-111">Betalningstjänstinställningarna på onlinebutikens utcheckningssida lagras i cacheminnet på Commerce Scale Unit och kan ta upp till 15 minuter att visa på webbplatsen för e-handel.</span><span class="sxs-lookup"><span data-stu-id="ff3e6-111">The payment service settings on the online store's checkout page are cached on the Commerce Scale Unit and can take up to 15 minutes to appear on the e-commerce site.</span></span> <span data-ttu-id="ff3e6-112">Dessa inställningar innefattar ändringar av konto-ID:t för handlare, molnbaserad API-nyckel och olika konfigurationsinställningar som gäller betalningsmetoden.</span><span class="sxs-lookup"><span data-stu-id="ff3e6-112">These payment service settings include changes to the merchant account ID, cloud API key, and various configuration settings that are related to the payment method.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ff3e6-113">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="ff3e6-113">Additional resources</span></span>

[<span data-ttu-id="ff3e6-114">Ställa in en onlinekanal</span><span class="sxs-lookup"><span data-stu-id="ff3e6-114">Set up an online channel</span></span>](../channel-setup-online.md)
