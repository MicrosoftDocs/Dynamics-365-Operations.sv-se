---
title: Fel vid ordersynkronisering relaterad till standardbetalningstjänsten
description: Det här avsnittet innehåller felsökningsvägledning som kan hjälpa till att korrigera ett fel som kan inträffa när en onlineorder synkroniseras.
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
ms.openlocfilehash: fa174bbb257379f6ce906dd21180bbcb19f8bc3f
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021137"
---
# <a name="order-synchronization-error-related-to-the-default-payment-service"></a><span data-ttu-id="d4356-103">Fel vid ordersynkronisering relaterad till standardbetalningstjänsten</span><span class="sxs-lookup"><span data-stu-id="d4356-103">Order synchronization error related to the default payment service</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="d4356-104">Det här avsnittet innehåller felsökningsvägledning som kan hjälpa till att korrigera ett fel som kan inträffa när en onlineorder synkroniseras.</span><span class="sxs-lookup"><span data-stu-id="d4356-104">This topic provides troubleshooting guidance that can help fix an error that might occur when an online order is synced.</span></span>

## <a name="description"></a><span data-ttu-id="d4356-105">beskrivning</span><span class="sxs-lookup"><span data-stu-id="d4356-105">Description</span></span>

<span data-ttu-id="d4356-106">När du synkroniserar en onlineorder visas följande felmeddelande: "Det måste finnas en standardbetalningstjänst för att bearbeta kreditkortstransaktioner."</span><span class="sxs-lookup"><span data-stu-id="d4356-106">When you sync an online order, you receive the following error message: "There must be a default payment service to process credit card transactions."</span></span>

![Standardbetalningstjänstfel saknas](media/default-payment-method-error.jpg)

## <a name="resolution"></a><span data-ttu-id="d4356-108">Upplösning</span><span class="sxs-lookup"><span data-stu-id="d4356-108">Resolution</span></span>

### <a name="confirm-or-set-the-default-payment-service-in-commerce-headquarters"></a><span data-ttu-id="d4356-109">Bekräfta eller ställ in standardbetalningstjänsten i Commerce-administration</span><span class="sxs-lookup"><span data-stu-id="d4356-109">Confirm or set the default payment service in Commerce headquarters</span></span>

<span data-ttu-id="d4356-110">Bekräfta eller ställ in standardbetalningstjänsten i Commerce-administration, följ dessa steg.</span><span class="sxs-lookup"><span data-stu-id="d4356-110">To confirm or set the default payment service in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="d4356-111">Gå till **Kundfordringar \> Betalningsinställning \> Betaltjänster**.</span><span class="sxs-lookup"><span data-stu-id="d4356-111">Go to **Accounts receivable \> Payment setup \> Payment services**.</span></span>
1. <span data-ttu-id="d4356-112">Se till att alternativet **Standardföretag för nya kreditkort** anges till **Ja** för en betalningstjänst.</span><span class="sxs-lookup"><span data-stu-id="d4356-112">Make sure that the **Default processor for new credit cards** option is set to **Yes** for one payment service.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d4356-113">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="d4356-113">Additional resources</span></span>

[<span data-ttu-id="d4356-114">Inställning, auktorisering och registrering av kreditkort</span><span class="sxs-lookup"><span data-stu-id="d4356-114">Credit card setup, authorization, and capture</span></span>](../../finance/accounts-receivable/credit-card-authorizations.md)