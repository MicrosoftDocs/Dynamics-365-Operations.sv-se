---
title: Vagnikonmodul
description: Det här avsnittet handlar om vagnikonmodulen och beskriver hur du lägger till den till webbsidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 10/20/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 5ff514f07e8b31abe79775e5011bd3f1b24b2935
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5793091"
---
# <a name="cart-icon-module"></a><span data-ttu-id="7a788-103">Ikon för kundvagnsmodul</span><span class="sxs-lookup"><span data-stu-id="7a788-103">Cart icon module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="7a788-104">Det här avsnittet handlar om vagnikonmodulen och beskriver hur du lägger till den till webbsidorna i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="7a788-104">This topic covers the cart icon module and describes how to add it to site pages in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="7a788-105">Vagnikonmodulen representerar kundvagnen i huvudmodulen på sidan och visar antalet artiklar i vagnen.</span><span class="sxs-lookup"><span data-stu-id="7a788-105">The cart icon module represents the cart in the header module of the page, and shows the number of items in the cart.</span></span> <span data-ttu-id="7a788-106">Vagnikonmodulen visar också en sammanfattning av kundvagnen (även kallad en minivagn) när vagnikonen hovras över.</span><span class="sxs-lookup"><span data-stu-id="7a788-106">The cart icon module also displays a cart summary (also known as a mini cart) when the cart icon is hovered over.</span></span> <span data-ttu-id="7a788-107">Minivagnen ger användaren en sammanfattning av artiklarna i kundvagnen utan att behöva navigera till kundvagnssidan.</span><span class="sxs-lookup"><span data-stu-id="7a788-107">The mini cart provides the user with a summary of the items in the cart without having to navigate to the cart page.</span></span> <span data-ttu-id="7a788-108">Dessutom kan användaren gå direkt till kassasidan om de är nöjda med sammanfattningen.</span><span class="sxs-lookup"><span data-stu-id="7a788-108">In addition, it also allows the user to directly go to checkout page if they are happy with the summary.</span></span> <span data-ttu-id="7a788-109">Detta minskar antalet sidnavigeringer och gör kassan snabbare.</span><span class="sxs-lookup"><span data-stu-id="7a788-109">This reduces the number of page navigations and makes checkout faster.</span></span> 

> [!NOTE]
> <span data-ttu-id="7a788-110">Stöd för modulen kundvagnikon i Dynamics 365 Commerce 10.0.11-versionen.</span><span class="sxs-lookup"><span data-stu-id="7a788-110">Support for the cart icon module is available in the Dynamics 365 Commerce 10.0.11 release.</span></span>

<span data-ttu-id="7a788-111">Följande bild visar ett exempel på en kundvagnsikon som visar en minikundvagn i Fabrikam-rubriken.</span><span class="sxs-lookup"><span data-stu-id="7a788-111">The following image shows an example of a cart icon module that displays a mini cart in the Fabrikam header.</span></span>

![Exempel på en modul för kundvagnsikon](./media/ecommerce-Minicart.PNG)

## <a name="module-properties"></a><span data-ttu-id="7a788-113">Modulegenskaper</span><span class="sxs-lookup"><span data-stu-id="7a788-113">Module properties</span></span>

- <span data-ttu-id="7a788-114">**Visa minivagn** – när värdet är sant kan den här egenskapen användas för att visa en sammanfattning av kundvagnen (minivagn) när man hovrar över vagnikonen.</span><span class="sxs-lookup"><span data-stu-id="7a788-114">**Show mini cart** – When true, this property enables a cart summary (mini cart) to be displayed when the cart icon is hovered over.</span></span> <span data-ttu-id="7a788-115">Den här funktionen stöds endast för portar i skrivbordsvy.</span><span class="sxs-lookup"><span data-stu-id="7a788-115">This functionality is only supported for desktop view ports.</span></span>

## <a name="add-a-cart-icon-module-to-a-page"></a><span data-ttu-id="7a788-116">Lägg till en vagnikonmodul på en ny sida</span><span class="sxs-lookup"><span data-stu-id="7a788-116">Add a cart icon module to a page</span></span>

<span data-ttu-id="7a788-117">Mer information om hur du lägger till en vagnikonmodul finns i [Huvudmodul](author-header-module.md).</span><span class="sxs-lookup"><span data-stu-id="7a788-117">To add a cart icon module, see [Header module](author-header-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="7a788-118">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="7a788-118">Additional resources</span></span>

[<span data-ttu-id="7a788-119">Kundvagnsmodul</span><span class="sxs-lookup"><span data-stu-id="7a788-119">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="7a788-120">Kassamodul</span><span class="sxs-lookup"><span data-stu-id="7a788-120">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="7a788-121">Betalningsmodul</span><span class="sxs-lookup"><span data-stu-id="7a788-121">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="7a788-122">Modul för leveransadress</span><span class="sxs-lookup"><span data-stu-id="7a788-122">Shipping address module</span></span>](ship-address-module.md)

[<span data-ttu-id="7a788-123">Modul för leveransalternativ</span><span class="sxs-lookup"><span data-stu-id="7a788-123">Delivery options module</span></span>](delivery-options-module.md)

[<span data-ttu-id="7a788-124">Informationsmodul för upphämtning</span><span class="sxs-lookup"><span data-stu-id="7a788-124">Pickup information module</span></span>](pickup-info-module.md)

[<span data-ttu-id="7a788-125">Orderinformationsmodul</span><span class="sxs-lookup"><span data-stu-id="7a788-125">Order details module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="7a788-126">Presentkortsmodul</span><span class="sxs-lookup"><span data-stu-id="7a788-126">Gift card module</span></span>](add-giftcard.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]