---
title: Vagnikonmodul
description: Det här avsnittet handlar om vagnikonmodulen och beskriver hur du lägger till den till webbsidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 138c256b56593c4fafb20050a97e614fa584597c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4997837"
---
# <a name="cart-icon-module"></a><span data-ttu-id="ef9c3-103">Vagnikonmodul</span><span class="sxs-lookup"><span data-stu-id="ef9c3-103">Cart icon module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="ef9c3-104">Det här avsnittet handlar om vagnikonmodulen och beskriver hur du lägger till den till webbsidorna i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="ef9c3-104">This topic covers the cart icon module and describes how to add it to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="ef9c3-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="ef9c3-105">Overview</span></span>

<span data-ttu-id="ef9c3-106">Vagnikonmodulen representerar kundvagnen i huvudmodulen på sidan och visar antalet artiklar i vagnen.</span><span class="sxs-lookup"><span data-stu-id="ef9c3-106">The cart icon module represents the cart in the header module of the page, and shows the number of items in the cart.</span></span> <span data-ttu-id="ef9c3-107">Vagnikonmodulen visar också en sammanfattning av kundvagnen (även kallad en minivagn) när vagnikonen hovras över.</span><span class="sxs-lookup"><span data-stu-id="ef9c3-107">The cart icon module also displays a cart summary (also known as a mini cart) when the cart icon is hovered over.</span></span> <span data-ttu-id="ef9c3-108">Minivagnen ger användaren en sammanfattning av artiklarna i kundvagnen utan att behöva navigera till kundvagnssidan.</span><span class="sxs-lookup"><span data-stu-id="ef9c3-108">The mini cart provides the user with a summary of the items in the cart without having to navigate to the cart page.</span></span> <span data-ttu-id="ef9c3-109">Dessutom kan användaren gå direkt till kassasidan om de är nöjda med sammanfattningen.</span><span class="sxs-lookup"><span data-stu-id="ef9c3-109">In addition, it also allows the user to directly go to checkout page if they are happy with the summary.</span></span> <span data-ttu-id="ef9c3-110">Detta minskar antalet sidnavigeringer och gör kassan snabbare.</span><span class="sxs-lookup"><span data-stu-id="ef9c3-110">This reduces the number of page navigations and makes checkout faster.</span></span> 

> [!NOTE]
> <span data-ttu-id="ef9c3-111">Stöd för modulen kundvagnikon i Dynamics 365 Commerce 10.0.11-versionen.</span><span class="sxs-lookup"><span data-stu-id="ef9c3-111">Support for the cart icon module is available in the Dynamics 365 Commerce 10.0.11 release.</span></span>

<span data-ttu-id="ef9c3-112">Följande bild visar ett exempel på en kundvagnsikon som visar en minikundvagn i Fabrikam-rubriken.</span><span class="sxs-lookup"><span data-stu-id="ef9c3-112">The following image shows an example of a cart icon module that displays a mini cart in the Fabrikam header.</span></span>

![Exempel på en modul för kundvagnsikon](./media/ecommerce-Minicart.PNG)

## <a name="module-properties"></a><span data-ttu-id="ef9c3-114">Modulegenskaper</span><span class="sxs-lookup"><span data-stu-id="ef9c3-114">Module properties</span></span>

- <span data-ttu-id="ef9c3-115">**Visa minivagn** – när värdet är sant kan den här egenskapen användas för att visa en sammanfattning av kundvagnen (minivagn) när man hovrar över vagnikonen.</span><span class="sxs-lookup"><span data-stu-id="ef9c3-115">**Show mini cart** – When true, this property enables a cart summary (mini cart) to be displayed when the cart icon is hovered over.</span></span> <span data-ttu-id="ef9c3-116">Den här funktionen stöds endast för portar i skrivbordsvy.</span><span class="sxs-lookup"><span data-stu-id="ef9c3-116">This functionality is only supported for desktop view ports.</span></span>

## <a name="add-a-cart-icon-module-to-a-page"></a><span data-ttu-id="ef9c3-117">Lägg till en vagnikonmodul på en ny sida</span><span class="sxs-lookup"><span data-stu-id="ef9c3-117">Add a cart icon module to a page</span></span>

<span data-ttu-id="ef9c3-118">Mer information om hur du lägger till en vagnikonmodul finns i [Huvudmodul](author-header-module.md).</span><span class="sxs-lookup"><span data-stu-id="ef9c3-118">To add a cart icon module, see [Header module](author-header-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ef9c3-119">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="ef9c3-119">Additional resources</span></span>

[<span data-ttu-id="ef9c3-120">Kundvagnsmodul</span><span class="sxs-lookup"><span data-stu-id="ef9c3-120">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="ef9c3-121">Kassamodul</span><span class="sxs-lookup"><span data-stu-id="ef9c3-121">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="ef9c3-122">Betalningsmodul</span><span class="sxs-lookup"><span data-stu-id="ef9c3-122">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="ef9c3-123">Modul för leveransadress</span><span class="sxs-lookup"><span data-stu-id="ef9c3-123">Shipping address module</span></span>](ship-address-module.md)

[<span data-ttu-id="ef9c3-124">Modul för leveransalternativ</span><span class="sxs-lookup"><span data-stu-id="ef9c3-124">Delivery options module</span></span>](delivery-options-module.md)

[<span data-ttu-id="ef9c3-125">Informationsmodul för upphämtning</span><span class="sxs-lookup"><span data-stu-id="ef9c3-125">Pickup information module</span></span>](pickup-info-module.md)

[<span data-ttu-id="ef9c3-126">Orderinformationsmodul</span><span class="sxs-lookup"><span data-stu-id="ef9c3-126">Order details module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="ef9c3-127">Presentkortsmodul</span><span class="sxs-lookup"><span data-stu-id="ef9c3-127">Gift card module</span></span>](add-giftcard.md)
