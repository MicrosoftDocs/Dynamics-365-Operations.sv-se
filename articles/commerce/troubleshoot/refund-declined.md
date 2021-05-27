---
title: Återbetalning på en returorder avvisas
description: Det här avsnittet innehåller felsökningsvägledning som kan vara till hjälp när en återbetalning av en returorder avvisas eftersom det kreditkort som används för fakturering skiljer sig från det kort som användes i den ursprungliga betalningsauktoriseringen.
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
ms.openlocfilehash: 99fd4b816b1a3a1fe3c2d1579be45b43fdc3d385
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020766"
---
# <a name="refund-on-a-return-order-is-declined"></a><span data-ttu-id="b557e-103">Återbetalning på en returorder avvisas</span><span class="sxs-lookup"><span data-stu-id="b557e-103">Refund on a return order is declined</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b557e-104">Det här avsnittet innehåller felsökningsvägledning som kan vara till hjälp när en återbetalning av en returorder avvisas eftersom det kreditkort som används för fakturering skiljer sig från det kort som användes i den ursprungliga betalningsauktoriseringen.</span><span class="sxs-lookup"><span data-stu-id="b557e-104">This topic provides troubleshooting guidance that can help when a refund on a return order is declined because the credit card that is used for invoicing differs from the card that was used during the original payment authorization.</span></span>

## <a name="description"></a><span data-ttu-id="b557e-105">beskrivning</span><span class="sxs-lookup"><span data-stu-id="b557e-105">Description</span></span>

<span data-ttu-id="b557e-106">En återbetalning avvisas när kreditkortet som används för att fakturera en returorder avviker från det kort som användes i den ursprungliga betalningsauktoriseringen.</span><span class="sxs-lookup"><span data-stu-id="b557e-106">A refund is declined when the credit card that is used to invoice a return order differs from the card that was used during the original payment authorization.</span></span> <span data-ttu-id="b557e-107">Du får följande felmeddelande: "Vissa betalningar har inte rätt status för bokföring.</span><span class="sxs-lookup"><span data-stu-id="b557e-107">You receive the following error message: "Some payments are not in the correct status for posting.</span></span> <span data-ttu-id="b557e-108">Validera statusen för alla betalningar före fakturering på ett annat sätt."</span><span class="sxs-lookup"><span data-stu-id="b557e-108">Please re-validate the status of all payments prior to invoicing."</span></span>

<span data-ttu-id="b557e-109">Detaljer om betalningsauktoriseringen innehåller följande felmeddelande: "Adyen gateway SendRequest() misslyckades med statusen InternalServerError'.22144; Tomt svar som returnerats från Adyen. (22001);"</span><span class="sxs-lookup"><span data-stu-id="b557e-109">The payment authorization details will include the following error message: "Adyen gateway SendRequest() failed with status 'InternalServerError'.22144; Empty response returned from Adyen.(22001);"</span></span>

![Avvisad återbetalning vid ett returorderfel](media/refund-order-decline.jpg)

## <a name="resolution"></a><span data-ttu-id="b557e-111">Upplösning</span><span class="sxs-lookup"><span data-stu-id="b557e-111">Resolution</span></span>

### <a name="enable-blind-returns-in-adyen"></a><span data-ttu-id="b557e-112">Aktivera blinda returer i Adyen</span><span class="sxs-lookup"><span data-stu-id="b557e-112">Enable blind returns in Adyen</span></span>

<span data-ttu-id="b557e-113">Om du vill aktivera blinda returer följer du stegen i [Felsöka Dynamics 365 Payment Connector för Adyen problem](adyen-support.md) för att kontakta Adyens supportteam och begära att blinda returer aktiveras på ditt Adyen-handelskonto.</span><span class="sxs-lookup"><span data-stu-id="b557e-113">To enable blind returns, follow the steps in [Troubleshoot Dynamics 365 Payment Connector for Adyen issues](adyen-support.md) to contact the Adyen support team and request that blind returns be enabled on your Adyen merchant account.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b557e-114">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="b557e-114">Additional resources</span></span>

[<span data-ttu-id="b557e-115">Dynamics 365-betalningskoppling för Adyen</span><span class="sxs-lookup"><span data-stu-id="b557e-115">Dynamics 365 Payment Connector for Adyen</span></span>](../dev-itpro/adyen-connector.md)

[<span data-ttu-id="b557e-116">Ställ in Adyen betalningskoppling för Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="b557e-116">Set up the Adyen payment connector for Dynamics 365</span></span>](https://docs.adyen.com/plugins/microsoft-dynamics)
