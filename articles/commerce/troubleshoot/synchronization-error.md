---
title: Fel vid ordersynkronisering relaterad till standardbetalningstjänsten
description: Det här avsnittet innehåller felsökningsvägledning som kan hjälpa till att korrigera ett fel som kan inträffa när en onlineorder synkroniseras.
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
ms.openlocfilehash: dd7c400f26b6fc7fbe1d4fec43a52295eb363333
ms.sourcegitcommit: 6c108be3378b365e6ec596a1a8666d59b758db25
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/12/2021
ms.locfileid: "5585531"
---
# <a name="order-synchronization-error-related-to-the-default-payment-service"></a><span data-ttu-id="d22ae-103">Fel vid ordersynkronisering relaterad till standardbetalningstjänsten</span><span class="sxs-lookup"><span data-stu-id="d22ae-103">Order synchronization error related to the default payment service</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="d22ae-104">Det här avsnittet innehåller felsökningsvägledning som kan hjälpa till att korrigera ett fel som kan inträffa när en onlineorder synkroniseras.</span><span class="sxs-lookup"><span data-stu-id="d22ae-104">This topic provides troubleshooting guidance that can help fix an error that might occur when an online order is synced.</span></span>

## <a name="description"></a><span data-ttu-id="d22ae-105">beskrivning</span><span class="sxs-lookup"><span data-stu-id="d22ae-105">Description</span></span>

<span data-ttu-id="d22ae-106">När du synkroniserar en onlineorder visas följande felmeddelande: "Det måste finnas en standardbetalningstjänst för att bearbeta kreditkortstransaktioner."</span><span class="sxs-lookup"><span data-stu-id="d22ae-106">When you sync an online order, you receive the following error message: "There must be a default payment service to process credit card transactions."</span></span>

![Standardbetalningstjänstfel saknas](media/default-payment-method-error.jpg)

## <a name="resolution"></a><span data-ttu-id="d22ae-108">Upplösning</span><span class="sxs-lookup"><span data-stu-id="d22ae-108">Resolution</span></span>

### <a name="confirm-or-set-the-default-payment-service-in-commerce-headquarters"></a><span data-ttu-id="d22ae-109">Bekräfta eller ställ in standardbetalningstjänsten i Commerce-administration</span><span class="sxs-lookup"><span data-stu-id="d22ae-109">Confirm or set the default payment service in Commerce headquarters</span></span>

<span data-ttu-id="d22ae-110">Bekräfta eller ställ in standardbetalningstjänsten i Commerce-administration, följ dessa steg.</span><span class="sxs-lookup"><span data-stu-id="d22ae-110">To confirm or set the default payment service in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="d22ae-111">Gå till **Kundfordringar \> Betalningsinställning \> Betaltjänster**.</span><span class="sxs-lookup"><span data-stu-id="d22ae-111">Go to **Accounts receivable \> Payment setup \> Payment services**.</span></span>
1. <span data-ttu-id="d22ae-112">Se till att alternativet **Standardföretag för nya kreditkort** anges till **Ja** för en betalningstjänst.</span><span class="sxs-lookup"><span data-stu-id="d22ae-112">Make sure that the **Default processor for new credit cards** option is set to **Yes** for one payment service.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d22ae-113">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="d22ae-113">Additional resources</span></span>

[<span data-ttu-id="d22ae-114">Inställning, auktorisering och registrering av kreditkort</span><span class="sxs-lookup"><span data-stu-id="d22ae-114">Credit card setup, authorization, and capture</span></span>](https://docs.microsoft.com/dynamics365/finance/accounts-receivable/credit-card-authorizations)
