---
title: Vagnikonmodul
description: Det här avsnittet handlar om vagnikonmodulen och beskriver hur du lägger till den till webbsidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 05/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 137debe3f4cad3948d20b2902ea80e66fa74ffd4
ms.sourcegitcommit: ae0843763a8b6b232bb71db326fab28605ac6c53
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2020
ms.locfileid: "3661157"
---
# <a name="cart-icon-module"></a><span data-ttu-id="ac729-103">Vagnikonmodul</span><span class="sxs-lookup"><span data-stu-id="ac729-103">Cart icon module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="ac729-104">Det här avsnittet handlar om vagnikonmodulen och beskriver hur du lägger till den till webbsidorna i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="ac729-104">This topic covers the cart icon module and describes how to add it to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="ac729-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="ac729-105">Overview</span></span>

<span data-ttu-id="ac729-106">Vagnikonmodulen representerar kundvagnen i huvudmodulen på sidan och visar antalet artiklar i vagnen.</span><span class="sxs-lookup"><span data-stu-id="ac729-106">The cart icon module represents the cart in the header module of the page, and shows the number of items in the cart.</span></span> <span data-ttu-id="ac729-107">Vagnikonmodulen visar också en sammanfattning av kundvagnen (även kallad en minivagn) när vagnikonen hovras över.</span><span class="sxs-lookup"><span data-stu-id="ac729-107">The cart icon module also displays a cart summary (also known as a mini cart) when the cart icon is hovered over.</span></span> <span data-ttu-id="ac729-108">Minivagnen ger användaren en sammanfattning av artiklarna i kundvagnen utan att behöva navigera till kundvagnssidan.</span><span class="sxs-lookup"><span data-stu-id="ac729-108">The mini cart provides the user with a summary of the items in the cart without having to navigate to the cart page.</span></span> <span data-ttu-id="ac729-109">Dessutom kan användaren gå direkt till kassasidan om de är nöjda med sammanfattningen.</span><span class="sxs-lookup"><span data-stu-id="ac729-109">In addition, it also allows the user to directly go to checkout page if they are happy with the summary.</span></span> <span data-ttu-id="ac729-110">Detta minskar antalet sidnavigeringer och gör utcheckningen snabbare.</span><span class="sxs-lookup"><span data-stu-id="ac729-110">This reduces the number of page navigations and makes checkout faster.</span></span> 

<span data-ttu-id="ac729-111">Följande bild visar ett exempel på en kundvagnsikon som visar en minikundvagn i Fabrikam-rubriken.</span><span class="sxs-lookup"><span data-stu-id="ac729-111">The following image shows an example of a cart icon module that displays a mini cart in the Fabrikam header.</span></span>

![Exempel på en modul för kundvagnsikon](./media/ecommerce-Minicart.PNG)

## <a name="module-properties"></a><span data-ttu-id="ac729-113">Modulegenskaper</span><span class="sxs-lookup"><span data-stu-id="ac729-113">Module properties</span></span>

- <span data-ttu-id="ac729-114">**Visa minivagn** – när värdet är sant kan den här egenskapen användas för att visa en sammanfattning av kundvagnen (minivagn) när man hovrar över vagnikonen.</span><span class="sxs-lookup"><span data-stu-id="ac729-114">**Show mini cart** – When true, this property enables a cart summary (mini cart) to be displayed when the cart icon is hovered over.</span></span> <span data-ttu-id="ac729-115">Den här funktionen stöds endast för portar i skrivbordsvy.</span><span class="sxs-lookup"><span data-stu-id="ac729-115">This functionality is only supported for desktop view ports.</span></span>

## <a name="add-a-cart-icon-module-to-a-page"></a><span data-ttu-id="ac729-116">Lägg till en vagnikonmodul på en ny sida</span><span class="sxs-lookup"><span data-stu-id="ac729-116">Add a cart icon module to a page</span></span>

<span data-ttu-id="ac729-117">Mer information om hur du lägger till en vagnikonmodul finns i [Huvudmodul](author-header-module.md).</span><span class="sxs-lookup"><span data-stu-id="ac729-117">To add a cart icon module, see [Header module](author-header-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ac729-118">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="ac729-118">Additional resources</span></span>

[<span data-ttu-id="ac729-119">Kundvagnsmodul</span><span class="sxs-lookup"><span data-stu-id="ac729-119">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="ac729-120">Kassamodul</span><span class="sxs-lookup"><span data-stu-id="ac729-120">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="ac729-121">Betalningsmodul</span><span class="sxs-lookup"><span data-stu-id="ac729-121">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="ac729-122">Modul för leveransadress</span><span class="sxs-lookup"><span data-stu-id="ac729-122">Shipping address module</span></span>](ship-address-module.md)

[<span data-ttu-id="ac729-123">Modul för leveransalternativ</span><span class="sxs-lookup"><span data-stu-id="ac729-123">Delivery options module</span></span>](delivery-options-module.md)

[<span data-ttu-id="ac729-124">Orderinformationsmodul</span><span class="sxs-lookup"><span data-stu-id="ac729-124">Order details module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="ac729-125">Presentkortsmodul</span><span class="sxs-lookup"><span data-stu-id="ac729-125">Gift card module</span></span>](add-giftcard.md)
