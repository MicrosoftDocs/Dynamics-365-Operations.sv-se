---
title: Presentkortsmodul
description: Det här avsnittet handlar om presentkortsmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 04/13/2020
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
ms.openlocfilehash: 70047376cec44523cc9cfe4df792bde23c776d8c
ms.sourcegitcommit: ac966ea3a6c557fb5f9634b187b0e788d3e82d4d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/14/2020
ms.locfileid: "3261591"
---
# <a name="gift-card-module"></a><span data-ttu-id="d1677-103">Presentkortsmodul</span><span class="sxs-lookup"><span data-stu-id="d1677-103">Gift card module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="d1677-104">Det här avsnittet handlar om presentkortsmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="d1677-104">This topic covers gift card modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="d1677-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="d1677-105">Overview</span></span>

<span data-ttu-id="d1677-106">Presentkort är en vanlig typ av betalning och presentkortsmodulen kan användas i en betalningsmodul för att ta emot presentkort.</span><span class="sxs-lookup"><span data-stu-id="d1677-106">Gift cards are a common form of payment, and the gift card module can be used in a checkout module to accept gift cards.</span></span> <span data-ttu-id="d1677-107">Presentkortsmodulen kan användas med Dynamics 365, SVS, och Givex presentkortskort.</span><span class="sxs-lookup"><span data-stu-id="d1677-107">The gift card module supports Dynamics 365, SVS, and Givex gift cards.</span></span> <span data-ttu-id="d1677-108">SVS och Givex presentkort löses in via Adyen betalningsförmedlaren.</span><span class="sxs-lookup"><span data-stu-id="d1677-108">SVS and Givex gift cards are redeemed via the Adyen payment provider.</span></span>

<span data-ttu-id="d1677-109">Mer information om stöd för externa presentkort, t.ex. SVS och Givex, se [Stöd för externa presentkort](./dev-itpro/gift-card.md)</span><span class="sxs-lookup"><span data-stu-id="d1677-109">For more information on support for external gift cards such as SVS and Givex, see [Support for external gift cards](./dev-itpro/gift-card.md)</span></span>

## <a name="module-properties"></a><span data-ttu-id="d1677-110">Modulegenskaper</span><span class="sxs-lookup"><span data-stu-id="d1677-110">Module properties</span></span>

- <span data-ttu-id="d1677-111">**Visa ytterligare fält** – den här egenskapen definierar vilka fält som ska visas för presentkort utöver presentkortsnumret, som alltid visas som standard.</span><span class="sxs-lookup"><span data-stu-id="d1677-111">**Show additional fields** - This property defines what fields should be displayed for gift cards in addition to the gift card number, which is always displayed by default.</span></span> <span data-ttu-id="d1677-112">Vissa presentkort stöder t.ex. ett personligt ID-nummer (PIN-kod) och andra support visar en PIN-kod och ett förfallodatum.</span><span class="sxs-lookup"><span data-stu-id="d1677-112">For example, some gift cards support displaying a personal identification number (PIN), and others support displaying a PIN and expiration date.</span></span> <span data-ttu-id="d1677-113">Alternativt kan den här egenskapen anges till "ingen", vilket bara visar presentkortsnumret och inga ytterligare fält.</span><span class="sxs-lookup"><span data-stu-id="d1677-113">Alternatively, this property could be set to "None", which would only display the gift card number and no additional fields.</span></span>

<span data-ttu-id="d1677-114">Värden som stöds:</span><span class="sxs-lookup"><span data-stu-id="d1677-114">Supported values:</span></span>
-   <span data-ttu-id="d1677-115">PIN-kod</span><span class="sxs-lookup"><span data-stu-id="d1677-115">PIN</span></span>
-   <span data-ttu-id="d1677-116">Utgångsdatum</span><span class="sxs-lookup"><span data-stu-id="d1677-116">Expiration date</span></span>
-   <span data-ttu-id="d1677-117">PIN och utgångsdatum</span><span class="sxs-lookup"><span data-stu-id="d1677-117">PIN and expiration date</span></span> 
-   <span data-ttu-id="d1677-118">None</span><span class="sxs-lookup"><span data-stu-id="d1677-118">None</span></span>

## <a name="site-settings-for-gift-card-modules"></a><span data-ttu-id="d1677-119">Platsinställningar för presentkortsmoduler</span><span class="sxs-lookup"><span data-stu-id="d1677-119">Site settings for gift card modules</span></span>

<span data-ttu-id="d1677-120">I Commerce webbplatsskaparen under **webbplatsinställnings \> tillägg**, finns en presentkorts inställning som kallas **presentkortstyp som stöds**.</span><span class="sxs-lookup"><span data-stu-id="d1677-120">In Commerce site builder under **Site Settings \> Extensions**, there is a gift card module setting called **Supported gift card type**.</span></span> <span data-ttu-id="d1677-121">Den här inställningen har stöd för tre värden:</span><span class="sxs-lookup"><span data-stu-id="d1677-121">This setting supports three values:</span></span>
- <span data-ttu-id="d1677-122">**Dynamics 365 presentkort** - när den här inställningen används tillåter presentkortet bara inlösen av Dynamics 365-presentkort.</span><span class="sxs-lookup"><span data-stu-id="d1677-122">**Dynamics 365 gift card** - When this setting is applied, the gift card module only allows the redemption of Dynamics 365 gift cards.</span></span> <span data-ttu-id="d1677-123">Den här inställningen stöds endast för inloggade användare på webbplatsen för e-handel.</span><span class="sxs-lookup"><span data-stu-id="d1677-123">This setting is only supported for signed-in users on the e-Commerce site.</span></span>
- <span data-ttu-id="d1677-124">**SVS- och Givex-presentkort** - när den här inställningen används tillåter presentkortet bara inlösen av SVS- och Givex-presentkort.</span><span class="sxs-lookup"><span data-stu-id="d1677-124">**SVS and Givex gift cards** - When this setting is applied, the gift card module only allows the redemption of Givex and SVS gift cards.</span></span> <span data-ttu-id="d1677-125">Den här inställningen stöds för inloggade anonyma användare på webbplatsen för e-handel.</span><span class="sxs-lookup"><span data-stu-id="d1677-125">This setting is supported for signed-in and anonymous users on the e-Commerce site.</span></span>
- <span data-ttu-id="d1677-126">**Dynamics 365, SVS- och Givex-presentkort** - när den här inställningen används tillåter presentkortet inlösen av Dynamics 365, Givex och SVS-presentkort.</span><span class="sxs-lookup"><span data-stu-id="d1677-126">**Dynamics 365, SVS, and Givex gift cards** - When this setting is applied, the gift card module allows the redemption of Dynamics 365, Givex, and SVS gift cards.</span></span> <span data-ttu-id="d1677-127">Den här inställningen stöds endast för inloggade användare på webbplatsen för e-handel.</span><span class="sxs-lookup"><span data-stu-id="d1677-127">This setting is only supported for signed-in users on the e-Commerce site.</span></span>

## <a name="add-a-gift-card-module-to-a-page"></a><span data-ttu-id="d1677-128">Lägg till presentkortmodulen på en ny sida</span><span class="sxs-lookup"><span data-stu-id="d1677-128">Add a gift card module to a page</span></span>

<span data-ttu-id="d1677-129">Instruktioner om hur du lägger till en presentkortsmodul på en betalningssida och anger de obligatoriska egenskaperna finns i [betalningsmodulen](add-checkout-module.md).</span><span class="sxs-lookup"><span data-stu-id="d1677-129">For instructions on how to add a gift card module to a checkout page and set the required properties, see [Checkout module](add-checkout-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d1677-130">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="d1677-130">Additional resources</span></span>

[<span data-ttu-id="d1677-131">Startpaket – översikt</span><span class="sxs-lookup"><span data-stu-id="d1677-131">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="d1677-132">Kassamodul</span><span class="sxs-lookup"><span data-stu-id="d1677-132">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="d1677-133">Stöd för externa presentkort</span><span class="sxs-lookup"><span data-stu-id="d1677-133">Support for external gift cards</span></span>](./dev-itpro/gift-card.md)
