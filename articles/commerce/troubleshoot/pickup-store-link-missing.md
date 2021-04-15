---
title: Hämtningsalternativet visas inte på informationssidorna för vagnen eller produkten
description: Det här avsnittet innehåller felsökningsvägledning som kan vara till hjälp när alternativet för upphämtning i butiken inte visas på vagnsidan eller produktinformationssidorna.
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
ms.openlocfilehash: 46eeed18bb547035603d7e9a01e8f131a2393f01
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5801637"
---
# <a name="pick-this-up-option-doesnt-appear-on-cart-or-product-details-pages"></a><span data-ttu-id="6935f-103">Hämtningsalternativet visas inte på informationssidorna för vagnen eller produkten</span><span class="sxs-lookup"><span data-stu-id="6935f-103">"Pick this up" option doesn't appear on cart or product details pages</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="6935f-104">Det här avsnittet innehåller felsökningsvägledning som kan vara till hjälp när alternativet för upphämtning i butiken inte visas på vagnsidan eller produktinformationssidorna.</span><span class="sxs-lookup"><span data-stu-id="6935f-104">This topic provides troubleshooting guidance that can help when the option for in-store pickup doesn't appear on the cart page or product details pages.</span></span>

## <a name="description"></a><span data-ttu-id="6935f-105">beskrivning</span><span class="sxs-lookup"><span data-stu-id="6935f-105">Description</span></span>

<span data-ttu-id="6935f-106">Knappen **Plocka upp** visas inte på informationssidorna för vagnen eller produkten.</span><span class="sxs-lookup"><span data-stu-id="6935f-106">The **Pick this up** button doesn't appear on the cart page or product details pages.</span></span>

<span data-ttu-id="6935f-107">I bilden nedan visas ett exempel på en sida där knappen **Plocka upp** finns.</span><span class="sxs-lookup"><span data-stu-id="6935f-107">The following illustration shows an example of a page that includes the **Pick this up** button.</span></span>

![Plocka upp den här knappen](media/pickup-button-missing.jpg)

## <a name="resolution"></a><span data-ttu-id="6935f-109">Upplösning</span><span class="sxs-lookup"><span data-stu-id="6935f-109">Resolution</span></span>

### <a name="enable-the-bopis-extension-in-commerce-site-builder"></a><span data-ttu-id="6935f-110">Aktivera BOPIS-filnamnstillägget i Commerce-webbplatsbyggaren</span><span class="sxs-lookup"><span data-stu-id="6935f-110">Enable the BOPIS extension in Commerce site builder</span></span>

<span data-ttu-id="6935f-111">Aktivera filnamnstillägget "handla online, upphämtning i butik" (BOPIS) i Commerce-webbplatsbyggaren genom att följa stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="6935f-111">To enable the "buy online, pick up in store" (BOPIS) extension in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="6935f-112">Välj din webbplats.</span><span class="sxs-lookup"><span data-stu-id="6935f-112">Select your site.</span></span>
1. <span data-ttu-id="6935f-113">Välj **webbplatsinställningar** och välj sedan **tillägg**.</span><span class="sxs-lookup"><span data-stu-id="6935f-113">Select **Site settings**, and then select **Extensions**.</span></span>
1. <span data-ttu-id="6935f-114">Kontrollera att alternativet **Inaktivera BOPIS** är avmarkerat.</span><span class="sxs-lookup"><span data-stu-id="6935f-114">Make sure that the **Disable BOPIS** option is cleared.</span></span>

### <a name="configure-modes-of-delivery-in-commerce-headquarters"></a><span data-ttu-id="6935f-115">Konfigurera leveranssätt i Commerce-administration</span><span class="sxs-lookup"><span data-stu-id="6935f-115">Configure modes of delivery in Commerce headquarters</span></span>

<span data-ttu-id="6935f-116">För att konfigurera leveranssätt i Commerce-administration, följ dessa steg.</span><span class="sxs-lookup"><span data-stu-id="6935f-116">To configure modes of delivery in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="6935f-117">Gå till **Anskaffning och källa \> Inställningar \> Leveranssätt**.</span><span class="sxs-lookup"><span data-stu-id="6935f-117">Go to **Procurement and sourcing \> Setup \> Modes of delivery**.</span></span>
1. <span data-ttu-id="6935f-118">Se till att ett leveranssätt **Kundplockning** har skapats och att produkter och adresser tilldelas den.</span><span class="sxs-lookup"><span data-stu-id="6935f-118">Make sure that a **Customer pickup** mode of delivery has been created, and that products and addresses are assigned to it.</span></span>
1. <span data-ttu-id="6935f-119">Öppna **Retail och Commerce \> Administrationsinställning \> Parametrar**.</span><span class="sxs-lookup"><span data-stu-id="6935f-119">Go to **Retail and Commerce \> Headquarters setup \> Parameters**.</span></span>
1. <span data-ttu-id="6935f-120">I navigeringsfönstret till vänster välj er du **Kundorder**.</span><span class="sxs-lookup"><span data-stu-id="6935f-120">In the left navigation, select **Customer orders**.</span></span>
1. <span data-ttu-id="6935f-121">Se till leveranssättet **Leveranssätt: upphämtning** är korrekt konfigurerat.</span><span class="sxs-lookup"><span data-stu-id="6935f-121">Make sure that **Pickup mode of delivery** is correctly configured.</span></span>

### <a name="configure-customer-orders-payments"></a><span data-ttu-id="6935f-122">Konfigurera kundorderbetalningar</span><span class="sxs-lookup"><span data-stu-id="6935f-122">Configure customer orders payments</span></span>

<span data-ttu-id="6935f-123">För att konfigurera kundorderbetalningar i Commerce-administration, följ dessa steg.</span><span class="sxs-lookup"><span data-stu-id="6935f-123">To configure customer orders payments in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="6935f-124">Öppna **Retail och Commerce \> Administrationsinställning \> Parametrar**.</span><span class="sxs-lookup"><span data-stu-id="6935f-124">Go to **Retail and Commerce \> Headquarters setup \> Parameters**.</span></span>
1. <span data-ttu-id="6935f-125">I navigeringsfönstret till vänster välj er du **Kundorder**.</span><span class="sxs-lookup"><span data-stu-id="6935f-125">In the left navigation, select **Customer orders**.</span></span>
1. <span data-ttu-id="6935f-126">På snabbfliken **Betalningar**, se till att fälten **Betalningsvillkor** och **Betalningsmetod** är korrekt inställda.</span><span class="sxs-lookup"><span data-stu-id="6935f-126">On the **Payments** FastTab, make sure that the **Terms of payment** and **Method of payment** fields are correctly set.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6935f-127">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="6935f-127">Additional resources</span></span>

[<span data-ttu-id="6935f-128">Konfigurera BOPIS</span><span class="sxs-lookup"><span data-stu-id="6935f-128">Configure BOPIS</span></span>](../cpe-bopis.md)

[<span data-ttu-id="6935f-129">Aktivera flera leveranssätt genom upphämtning för kundorder</span><span class="sxs-lookup"><span data-stu-id="6935f-129">Enable multiple pickup delivery modes for customer orders</span></span>](../multiple-pickup-modes.md)

[<span data-ttu-id="6935f-130">Flerkanals orderbetalningar för Commerce</span><span class="sxs-lookup"><span data-stu-id="6935f-130">Omni-channel Commerce order payments</span></span>](../dev-itpro/commerce-payments.md)

[<span data-ttu-id="6935f-131">Modul för butiksväljare</span><span class="sxs-lookup"><span data-stu-id="6935f-131">Store selector module</span></span>](../store-selector.md)
