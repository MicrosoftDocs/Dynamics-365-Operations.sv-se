---
title: Presentkortsmodul
description: Det här avsnittet handlar om presentkortsmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 08/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 4cc947b9d6f3cfa51bce2155170c49e9529d0f7d
ms.sourcegitcommit: 420b9e538f706178f8e1f2786e02f4f400bf2336
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/02/2020
ms.locfileid: "3761091"
---
# <a name="gift-card-module"></a><span data-ttu-id="3e590-103">Presentkortsmodul</span><span class="sxs-lookup"><span data-stu-id="3e590-103">Gift card module</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="3e590-104">Det här avsnittet handlar om presentkortsmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="3e590-104">This topic covers gift card modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="3e590-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="3e590-105">Overview</span></span>

<span data-ttu-id="3e590-106">Presentkortmoduler är en vanlig typ av betalningsmoduler för att acceptera presentkort, en vanlig betalningsmetod för e-handelstransaktioner.</span><span class="sxs-lookup"><span data-stu-id="3e590-106">Gift card modules can be used in checkout modules to accept gift cards, a common form of payment used for e-Commerce transactions.</span></span> <span data-ttu-id="3e590-107">Presentkortsmodulen kan användas med Dynamics 365, SVS, och Givex presentkortskort.</span><span class="sxs-lookup"><span data-stu-id="3e590-107">The gift card module supports Dynamics 365, SVS, and Givex gift cards.</span></span> <span data-ttu-id="3e590-108">SVS och Givex presentkort löses in via Adyen betalningsförmedlaren.</span><span class="sxs-lookup"><span data-stu-id="3e590-108">SVS and Givex gift cards are redeemed via the Adyen payment provider.</span></span> <span data-ttu-id="3e590-109">Mer information om stöd för externa presentkort, t.ex. SVS och Givex, se [Stöd för externa presentkort](./dev-itpro/gift-card.md).</span><span class="sxs-lookup"><span data-stu-id="3e590-109">For more information about support for external gift cards such as SVS and Givex, see [Support for external gift cards](./dev-itpro/gift-card.md).</span></span>

<span data-ttu-id="3e590-110">Det finns två tillgängliga presentkortmoduler:</span><span class="sxs-lookup"><span data-stu-id="3e590-110">There are two gift card modules available:</span></span>

- <span data-ttu-id="3e590-111">**Presentkort** – den här modulen kan användas på en betalningssida för att lösa in ett presentkort som betalningsmedel.</span><span class="sxs-lookup"><span data-stu-id="3e590-111">**Gift card** - This module can be used on a checkout page to redeem a gift card as tender.</span></span> 
- <span data-ttu-id="3e590-112">**Kontroll av presentkortssaldo** – den här modulen kan användas på alla sidor för att kontrollera saldot på ett presentkort.</span><span class="sxs-lookup"><span data-stu-id="3e590-112">**Gift card balance check** - This module can be used on any page to check the balance on a gift card.</span></span> <span data-ttu-id="3e590-113">Den här modulen är tillgänglig i Commerce version 10.0.14 och senare.</span><span class="sxs-lookup"><span data-stu-id="3e590-113">This module is available in Commerce release 10.0.14 and later.</span></span>

<span data-ttu-id="3e590-114">Följande bild visar ett exempel på en presentkortmodul på en kassasida.</span><span class="sxs-lookup"><span data-stu-id="3e590-114">The following image shows an example of a gift card module on a checkout page.</span></span>

![Exempel på en presentkortsmodul](./media/ecommerce-giftcard.PNG)

## <a name="module-properties"></a><span data-ttu-id="3e590-116">Modulegenskaper</span><span class="sxs-lookup"><span data-stu-id="3e590-116">Module properties</span></span>

- <span data-ttu-id="3e590-117">**Visa ytterligare fält** – den här egenskapen definierar vilka fält som ska visas för presentkort utöver presentkortsnumret, som alltid visas som standard.</span><span class="sxs-lookup"><span data-stu-id="3e590-117">**Show additional fields** - This property defines what fields should be displayed for gift cards in addition to the gift card number, which is always displayed by default.</span></span> <span data-ttu-id="3e590-118">Vissa presentkort stöder t.ex. ett personligt ID-nummer (PIN-kod) och andra support visar en PIN-kod och ett förfallodatum.</span><span class="sxs-lookup"><span data-stu-id="3e590-118">For example, some gift cards support displaying a personal identification number (PIN), and others support displaying a PIN and expiration date.</span></span> <span data-ttu-id="3e590-119">Alternativt kan den här egenskapen anges till "ingen", vilket bara visar presentkortsnumret och inga ytterligare fält.</span><span class="sxs-lookup"><span data-stu-id="3e590-119">Alternatively, this property could be set to "None", which would only display the gift card number and no additional fields.</span></span>

<span data-ttu-id="3e590-120">Värden som stöds:</span><span class="sxs-lookup"><span data-stu-id="3e590-120">Supported values:</span></span>
-   <span data-ttu-id="3e590-121">PIN-kod</span><span class="sxs-lookup"><span data-stu-id="3e590-121">PIN</span></span>
-   <span data-ttu-id="3e590-122">Utgångsdatum</span><span class="sxs-lookup"><span data-stu-id="3e590-122">Expiration date</span></span>
-   <span data-ttu-id="3e590-123">PIN och utgångsdatum</span><span class="sxs-lookup"><span data-stu-id="3e590-123">PIN and expiration date</span></span> 
-   <span data-ttu-id="3e590-124">None</span><span class="sxs-lookup"><span data-stu-id="3e590-124">None</span></span>

## <a name="site-settings-for-gift-card-modules"></a><span data-ttu-id="3e590-125">Platsinställningar för presentkortsmoduler</span><span class="sxs-lookup"><span data-stu-id="3e590-125">Site settings for gift card modules</span></span>

<span data-ttu-id="3e590-126">I Commerce webbplatsskaparen under **webbplatsinställnings \> tillägg**, finns en presentkorts inställning som kallas **presentkortstyp som stöds**.</span><span class="sxs-lookup"><span data-stu-id="3e590-126">In Commerce site builder under **Site Settings \> Extensions**, there is a gift card module setting called **Supported gift card type**.</span></span> <span data-ttu-id="3e590-127">Den här inställningen har stöd för tre värden:</span><span class="sxs-lookup"><span data-stu-id="3e590-127">This setting supports three values:</span></span>
- <span data-ttu-id="3e590-128">**Dynamics 365 presentkort** - när den här inställningen används tillåter presentkortet bara inlösen av Dynamics 365-presentkort.</span><span class="sxs-lookup"><span data-stu-id="3e590-128">**Dynamics 365 gift card** - When this setting is applied, the gift card module only allows the redemption of Dynamics 365 gift cards.</span></span> <span data-ttu-id="3e590-129">Den här inställningen stöds endast för inloggade användare på webbplatsen för e-handel.</span><span class="sxs-lookup"><span data-stu-id="3e590-129">This setting is only supported for signed-in users on the e-Commerce site.</span></span>
- <span data-ttu-id="3e590-130">**SVS- och Givex-presentkort** - när den här inställningen används tillåter presentkortet bara inlösen av SVS- och Givex-presentkort.</span><span class="sxs-lookup"><span data-stu-id="3e590-130">**SVS and Givex gift cards** - When this setting is applied, the gift card module only allows the redemption of Givex and SVS gift cards.</span></span> <span data-ttu-id="3e590-131">Den här inställningen stöds för inloggade anonyma användare på webbplatsen för e-handel.</span><span class="sxs-lookup"><span data-stu-id="3e590-131">This setting is supported for signed-in and anonymous users on the e-Commerce site.</span></span>
- <span data-ttu-id="3e590-132">**Dynamics 365, SVS- och Givex-presentkort** - när den här inställningen används tillåter presentkortet inlösen av Dynamics 365, Givex och SVS-presentkort.</span><span class="sxs-lookup"><span data-stu-id="3e590-132">**Dynamics 365, SVS, and Givex gift cards** - When this setting is applied, the gift card module allows the redemption of Dynamics 365, Givex, and SVS gift cards.</span></span> <span data-ttu-id="3e590-133">Den här inställningen stöds endast för inloggade användare på webbplatsen för e-handel.</span><span class="sxs-lookup"><span data-stu-id="3e590-133">This setting is only supported for signed-in users on the e-Commerce site.</span></span>

## <a name="add-a-gift-card-module-to-a-page"></a><span data-ttu-id="3e590-134">Lägg till presentkortmodulen på en ny sida</span><span class="sxs-lookup"><span data-stu-id="3e590-134">Add a gift card module to a page</span></span>

<span data-ttu-id="3e590-135">Instruktioner om hur du lägger till en presentkortsmodul på en betalningssida och anger de obligatoriska egenskaperna finns i [betalningsmodulen](add-checkout-module.md).</span><span class="sxs-lookup"><span data-stu-id="3e590-135">For instructions on how to add a gift card module to a checkout page and set the required properties, see [Checkout module](add-checkout-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="3e590-136">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="3e590-136">Additional resources</span></span>

[<span data-ttu-id="3e590-137">Kundvagnsmodul</span><span class="sxs-lookup"><span data-stu-id="3e590-137">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="3e590-138">Ikon för kundvagnsmodul</span><span class="sxs-lookup"><span data-stu-id="3e590-138">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="3e590-139">Kassamodul</span><span class="sxs-lookup"><span data-stu-id="3e590-139">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="3e590-140">Betalningsmodul</span><span class="sxs-lookup"><span data-stu-id="3e590-140">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="3e590-141">Modul för leveransadress</span><span class="sxs-lookup"><span data-stu-id="3e590-141">Shipping address module</span></span>](ship-address-module.md)

[<span data-ttu-id="3e590-142">Modul för leveransalternativ</span><span class="sxs-lookup"><span data-stu-id="3e590-142">Delivery options module</span></span>](delivery-options-module.md)

[<span data-ttu-id="3e590-143">Orderinformationsmodul</span><span class="sxs-lookup"><span data-stu-id="3e590-143">Order details module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="3e590-144">Stöd för externa presentkort</span><span class="sxs-lookup"><span data-stu-id="3e590-144">Support for external gift cards</span></span>](./dev-itpro/gift-card.md)
