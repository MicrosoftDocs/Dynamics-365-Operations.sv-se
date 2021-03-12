---
title: Presentkortsmodul
description: Det här avsnittet handlar om presentkortsmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: d9626f33ced0433bc96ed58429e95d4f75af6508
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4980392"
---
# <a name="gift-card-module"></a><span data-ttu-id="e48d7-103">Presentkortsmodul</span><span class="sxs-lookup"><span data-stu-id="e48d7-103">Gift card module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="e48d7-104">Det här avsnittet handlar om presentkortsmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="e48d7-104">This topic covers gift card modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="e48d7-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="e48d7-105">Overview</span></span>

<span data-ttu-id="e48d7-106">Presentkortmoduler är en vanlig typ av betalningsmoduler för att acceptera presentkort, en vanlig betalningsmetod för näthandelstransaktioner.</span><span class="sxs-lookup"><span data-stu-id="e48d7-106">Gift card modules can be used in checkout modules to accept gift cards, a common form of payment used for e-Commerce transactions.</span></span> <span data-ttu-id="e48d7-107">Presentkortsmodulen kan användas med Dynamics 365, SVS, och Givex presentkortskort.</span><span class="sxs-lookup"><span data-stu-id="e48d7-107">The gift card module supports Dynamics 365, SVS, and Givex gift cards.</span></span> <span data-ttu-id="e48d7-108">SVS och Givex presentkort löses in via Adyen betalningsförmedlaren.</span><span class="sxs-lookup"><span data-stu-id="e48d7-108">SVS and Givex gift cards are redeemed via the Adyen payment provider.</span></span> <span data-ttu-id="e48d7-109">Mer information om stöd för externa presentkort, t.ex. SVS och Givex, se [Stöd för externa presentkort](./dev-itpro/gift-card.md).</span><span class="sxs-lookup"><span data-stu-id="e48d7-109">For more information about support for external gift cards such as SVS and Givex, see [Support for external gift cards](./dev-itpro/gift-card.md).</span></span>

> [!NOTE]
> <span data-ttu-id="e48d7-110">Stöd för att lösa in SVS och Givex presentkort under kassaflödet är tillgängligt i Dynamics 365 Commerce 10.0.11-versionen.</span><span class="sxs-lookup"><span data-stu-id="e48d7-110">Support for redeeming SVS and Givex gift cards during checkout flow is available in the Dynamics 365 Commerce 10.0.11 release.</span></span> 

<span data-ttu-id="e48d7-111">Det finns två tillgängliga presentkortmoduler:</span><span class="sxs-lookup"><span data-stu-id="e48d7-111">There are two gift card modules available:</span></span>

- <span data-ttu-id="e48d7-112">**Presentkort** – den här modulen kan användas på en betalningssida för att lösa in ett presentkort som betalningsmedel.</span><span class="sxs-lookup"><span data-stu-id="e48d7-112">**Gift card** - This module can be used on a checkout page to redeem a gift card as tender.</span></span> 
- <span data-ttu-id="e48d7-113">**Kontroll av presentkortssaldo** – den här modulen kan användas på alla sidor för att kontrollera saldot på ett presentkort.</span><span class="sxs-lookup"><span data-stu-id="e48d7-113">**Gift card balance check** - This module can be used on any page to check the balance on a gift card.</span></span> <span data-ttu-id="e48d7-114">Den här modulen är tillgänglig i Commerce version 10.0.14 och senare.</span><span class="sxs-lookup"><span data-stu-id="e48d7-114">This module is available in Commerce release 10.0.14 and later.</span></span>

> [!NOTE]
> <span data-ttu-id="e48d7-115">Stödet för modulen Kontroll av presentkortssaldo är tillgänglig i Dynamics 365 Commerce 10.0.14-versionen.</span><span class="sxs-lookup"><span data-stu-id="e48d7-115">Support for the gift card balance check module is available in the Dynamics 365 Commerce 10.0.14 release.</span></span>

<span data-ttu-id="e48d7-116">Följande bild visar ett exempel på en presentkortmodul på en kassasida.</span><span class="sxs-lookup"><span data-stu-id="e48d7-116">The following image shows an example of a gift card module on a checkout page.</span></span>

![Exempel på en presentkortsmodul](./media/ecommerce-giftcard.PNG)

## <a name="module-properties"></a><span data-ttu-id="e48d7-118">Modulegenskaper</span><span class="sxs-lookup"><span data-stu-id="e48d7-118">Module properties</span></span>

- <span data-ttu-id="e48d7-119">**Visa ytterligare fält** – den här egenskapen definierar vilka fält som ska visas för presentkort utöver presentkortsnumret, som alltid visas som standard.</span><span class="sxs-lookup"><span data-stu-id="e48d7-119">**Show additional fields** - This property defines what fields should be displayed for gift cards in addition to the gift card number, which is always displayed by default.</span></span> <span data-ttu-id="e48d7-120">Vissa presentkort stöder t.ex. ett personligt ID-nummer (PIN-kod) och andra support visar en PIN-kod och ett förfallodatum.</span><span class="sxs-lookup"><span data-stu-id="e48d7-120">For example, some gift cards support displaying a personal identification number (PIN), and others support displaying a PIN and expiration date.</span></span> <span data-ttu-id="e48d7-121">Alternativt kan den här egenskapen anges till "ingen", vilket bara visar presentkortsnumret och inga ytterligare fält.</span><span class="sxs-lookup"><span data-stu-id="e48d7-121">Alternatively, this property could be set to "None", which would only display the gift card number and no additional fields.</span></span>

<span data-ttu-id="e48d7-122">Värden som stöds:</span><span class="sxs-lookup"><span data-stu-id="e48d7-122">Supported values:</span></span>
-   <span data-ttu-id="e48d7-123">PIN-kod</span><span class="sxs-lookup"><span data-stu-id="e48d7-123">PIN</span></span>
-   <span data-ttu-id="e48d7-124">Utgångsdatum</span><span class="sxs-lookup"><span data-stu-id="e48d7-124">Expiration date</span></span>
-   <span data-ttu-id="e48d7-125">PIN och utgångsdatum</span><span class="sxs-lookup"><span data-stu-id="e48d7-125">PIN and expiration date</span></span> 
-   <span data-ttu-id="e48d7-126">None</span><span class="sxs-lookup"><span data-stu-id="e48d7-126">None</span></span>

## <a name="site-settings-for-gift-card-modules"></a><span data-ttu-id="e48d7-127">Platsinställningar för presentkortsmoduler</span><span class="sxs-lookup"><span data-stu-id="e48d7-127">Site settings for gift card modules</span></span>

<span data-ttu-id="e48d7-128">I Commerce webbplatsskaparen under **webbplatsinställnings \> tillägg**, finns en presentkorts inställning som kallas **presentkortstyp som stöds**.</span><span class="sxs-lookup"><span data-stu-id="e48d7-128">In Commerce site builder under **Site Settings \> Extensions**, there is a gift card module setting called **Supported gift card type**.</span></span> <span data-ttu-id="e48d7-129">Den här inställningen har stöd för tre värden:</span><span class="sxs-lookup"><span data-stu-id="e48d7-129">This setting supports three values:</span></span>
- <span data-ttu-id="e48d7-130">**Dynamics 365 presentkort** – när den här inställningen används tillåter presentkortet bara inlösen av Dynamics 365-presentkort.</span><span class="sxs-lookup"><span data-stu-id="e48d7-130">**Dynamics 365 gift card** - When this setting is applied, the gift card module only allows the redemption of Dynamics 365 gift cards.</span></span> <span data-ttu-id="e48d7-131">Den här inställningen stöds endast för inloggade användare på webbplatsen för näthandel.</span><span class="sxs-lookup"><span data-stu-id="e48d7-131">This setting is only supported for signed-in users on the e-Commerce site.</span></span>
- <span data-ttu-id="e48d7-132">**SVS- och Givex-presentkort** – när den här inställningen används tillåter presentkortet bara inlösen av SVS- och Givex-presentkort.</span><span class="sxs-lookup"><span data-stu-id="e48d7-132">**SVS and Givex gift cards** - When this setting is applied, the gift card module only allows the redemption of Givex and SVS gift cards.</span></span> <span data-ttu-id="e48d7-133">Den här inställningen stöds för inloggade anonyma användare på webbplatsen för näthandel.</span><span class="sxs-lookup"><span data-stu-id="e48d7-133">This setting is supported for signed-in and anonymous users on the e-Commerce site.</span></span>
- <span data-ttu-id="e48d7-134">**Dynamics 365, SVS- och Givex-presentkort** – när den här inställningen används tillåter presentkortet inlösen av Dynamics 365, Givex och SVS-presentkort.</span><span class="sxs-lookup"><span data-stu-id="e48d7-134">**Dynamics 365, SVS, and Givex gift cards** - When this setting is applied, the gift card module allows the redemption of Dynamics 365, Givex, and SVS gift cards.</span></span> <span data-ttu-id="e48d7-135">Den här inställningen stöds endast för inloggade användare på webbplatsen för näthandel.</span><span class="sxs-lookup"><span data-stu-id="e48d7-135">This setting is only supported for signed-in users on the e-Commerce site.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e48d7-136">Dessa inställningar är tillgängliga i Dynamics 365 Commerce 10.0.11-versionen och krävs endast om du behöver stöd för SVS eller Givex presentkort.</span><span class="sxs-lookup"><span data-stu-id="e48d7-136">These settings are available in the Dynamics 365 Commerce 10.0.11 release and are required only if you need support for SVS or Givex gift cards.</span></span> <span data-ttu-id="e48d7-137">Om du uppdaterar från en äldre version av Dynamics 365 Commerce måste du uppdatera filen appsettings.json manuellt.</span><span class="sxs-lookup"><span data-stu-id="e48d7-137">If you are updating from an older version of Dynamics 365 Commerce, you must manually update the appsettings.json file.</span></span> <span data-ttu-id="e48d7-138">Information om hur du uppdaterar filen appsettings.json finns i [SDK- och modulens biblioteksuppdateringar](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).</span><span class="sxs-lookup"><span data-stu-id="e48d7-138">For instructions on updating the appsettings.json file, see [SDK and module library updates](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).</span></span> 

## <a name="add-a-gift-card-module-to-a-page"></a><span data-ttu-id="e48d7-139">Lägg till presentkortmodulen på en ny sida</span><span class="sxs-lookup"><span data-stu-id="e48d7-139">Add a gift card module to a page</span></span>

<span data-ttu-id="e48d7-140">Instruktioner om hur du lägger till en presentkortsmodul på en betalningssida och anger de obligatoriska egenskaperna finns i [betalningsmodulen](add-checkout-module.md).</span><span class="sxs-lookup"><span data-stu-id="e48d7-140">For instructions on how to add a gift card module to a checkout page and set the required properties, see [Checkout module](add-checkout-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e48d7-141">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="e48d7-141">Additional resources</span></span>

[<span data-ttu-id="e48d7-142">Kundvagnsmodul</span><span class="sxs-lookup"><span data-stu-id="e48d7-142">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="e48d7-143">Ikon för kundvagnsmodul</span><span class="sxs-lookup"><span data-stu-id="e48d7-143">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="e48d7-144">Kassamodul</span><span class="sxs-lookup"><span data-stu-id="e48d7-144">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="e48d7-145">Betalningsmodul</span><span class="sxs-lookup"><span data-stu-id="e48d7-145">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="e48d7-146">Modul för leveransadress</span><span class="sxs-lookup"><span data-stu-id="e48d7-146">Shipping address module</span></span>](ship-address-module.md)

[<span data-ttu-id="e48d7-147">Modul för leveransalternativ</span><span class="sxs-lookup"><span data-stu-id="e48d7-147">Delivery options module</span></span>](delivery-options-module.md)

[<span data-ttu-id="e48d7-148">Informationsmodul för upphämtning</span><span class="sxs-lookup"><span data-stu-id="e48d7-148">Pickup information module</span></span>](pickup-info-module.md)

[<span data-ttu-id="e48d7-149">Orderinformationsmodul</span><span class="sxs-lookup"><span data-stu-id="e48d7-149">Order details module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="e48d7-150">Stöd för externa presentkort</span><span class="sxs-lookup"><span data-stu-id="e48d7-150">Support for external gift cards</span></span>](./dev-itpro/gift-card.md)

[<span data-ttu-id="e48d7-151">Uppdateringar av SDK och modulbibliotek</span><span class="sxs-lookup"><span data-stu-id="e48d7-151">SDK and module library updates</span></span>](e-commerce-extensibility/sdk-updates.md)
