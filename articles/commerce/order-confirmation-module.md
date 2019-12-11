---
title: Orderbekräftelsemodulen
description: Det här avsnittet handlar om orderbekräftelsemoduler och beskriver hur du skapar dem i Microsoft Dynamics 365 Commerce.
author: anupamar
manager: annbe
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar-ms
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: e339ce02bb646d0d9a68c22b24fde9b72071de6f
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/01/2019
ms.locfileid: "2698336"
---
# <a name="order-confirmation-module"></a><span data-ttu-id="0bd13-103">Orderbekräftelsemodulen</span><span class="sxs-lookup"><span data-stu-id="0bd13-103">Order confirmation module</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="0bd13-104">Det här avsnittet handlar om orderbekräftelsemoduler och beskriver hur du skapar dem i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="0bd13-104">This topic covers order confirmation modules and describes how to create them in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="0bd13-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="0bd13-105">Overview</span></span>

<span data-ttu-id="0bd13-106">En orderbekräftelsemodul används för att visa ett bekräftelsemeddelande på en orderbekräftelsesida när en order har placerats.</span><span class="sxs-lookup"><span data-stu-id="0bd13-106">An order confirmation module is used to show a confirmation message on an order confirmation page after an order is placed.</span></span> <span data-ttu-id="0bd13-107">I orderbekräftelsemodulen visas orderbekräftelsenumret och den kund-e-postadress som tillhandahölls i kassan.</span><span class="sxs-lookup"><span data-stu-id="0bd13-107">The order confirmation module shows the order confirmation number and the customer email address that was provided during checkout.</span></span>

<span data-ttu-id="0bd13-108">När en order placeras i kassan skickas orderbekräftelsenumret och kundens e-postadress till sidan orderbekräftelse som en frågesträng i sidans URL.</span><span class="sxs-lookup"><span data-stu-id="0bd13-108">When an order is placed during checkout, the order confirmation number and customer email address are passed to the order confirmation page as a query string in the page's URL.</span></span> <span data-ttu-id="0bd13-109">Orderbekräftelsemodulen tar emot den här informationen och återger orderstatusen på orderbekräftelsesidan.</span><span class="sxs-lookup"><span data-stu-id="0bd13-109">The order confirmation module receives this information and renders the order status on the order confirmation page.</span></span> <span data-ttu-id="0bd13-110">Orderbekräftelsemodulen kräver den här sidkontexten för att ange orderns status.</span><span class="sxs-lookup"><span data-stu-id="0bd13-110">The order confirmation module requires this page context to provide the status of the order.</span></span>

## <a name="order-confirmation-module-properties"></a><span data-ttu-id="0bd13-111">Egenskaper för orderbekräftelsemodul</span><span class="sxs-lookup"><span data-stu-id="0bd13-111">Order confirmation module properties</span></span>

| <span data-ttu-id="0bd13-112">Egenskapsnamn</span><span class="sxs-lookup"><span data-stu-id="0bd13-112">Property name</span></span> | <span data-ttu-id="0bd13-113">Värden</span><span class="sxs-lookup"><span data-stu-id="0bd13-113">Values</span></span> | <span data-ttu-id="0bd13-114">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="0bd13-114">Description</span></span> |
|---------------|--------|-------------|
| <span data-ttu-id="0bd13-115">Rubrik</span><span class="sxs-lookup"><span data-stu-id="0bd13-115">Heading</span></span>       | <span data-ttu-id="0bd13-116">Rubriktext och rubriktagg (**H1**, **H2**, **H3**, **H4**, **H5** eller **H6**)</span><span class="sxs-lookup"><span data-stu-id="0bd13-116">Heading text and heading tag (**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**)</span></span> | <span data-ttu-id="0bd13-117">Orderbekräftelsemodulen kan ha en rubrik.</span><span class="sxs-lookup"><span data-stu-id="0bd13-117">The order confirmation module can have a heading.</span></span> <span data-ttu-id="0bd13-118">Som standard används rubriktaggen **H2** för rubriken.</span><span class="sxs-lookup"><span data-stu-id="0bd13-118">By default, the **H2** heading tag is used for the heading.</span></span> <span data-ttu-id="0bd13-119">Taggen kan emellertid ändras så att den uppfyller tillgänglighetskraven.</span><span class="sxs-lookup"><span data-stu-id="0bd13-119">However, the tag can be changed to meet accessibility requirements.</span></span> |

## <a name="modules-that-can-be-used-in-an-order-confirmation-page-module"></a><span data-ttu-id="0bd13-120">Moduler som kan användas på en sida för orderbekräftelsemodul</span><span class="sxs-lookup"><span data-stu-id="0bd13-120">Modules that can be used in an order confirmation page module</span></span> 

- <span data-ttu-id="0bd13-121">**Rekommendationer** – modulen rekommendationer kan placeras på sidan orderbekräftelse för att föreslå andra produkter till kunden.</span><span class="sxs-lookup"><span data-stu-id="0bd13-121">**Recommendations** – The recommendations module can be put on the order confirmation page to suggest other products to the customer.</span></span>
- <span data-ttu-id="0bd13-122">**Marknadsföring** – marknadsföringsmodulen kan lägga till marknadsföringsinnehåll på sidan orderbekräftelse.</span><span class="sxs-lookup"><span data-stu-id="0bd13-122">**Marketing** – The marketing module can add marketing content to the order confirmation page.</span></span>

## <a name="create-an-order-confirmation-page-module"></a><span data-ttu-id="0bd13-123">Skapa en sida för modul för orderbekräftelse</span><span class="sxs-lookup"><span data-stu-id="0bd13-123">Create an order confirmation page module</span></span>

1. <span data-ttu-id="0bd13-124">Skapa en sidmall som har namnet **orderbekräftelsemall**.</span><span class="sxs-lookup"><span data-stu-id="0bd13-124">Create a page template that is named **order confirmation template**.</span></span>
1. <span data-ttu-id="0bd13-125">Lägg till platsen **Huvud** på standardsida, lägg till orderbekräftelsemodul.</span><span class="sxs-lookup"><span data-stu-id="0bd13-125">In the **Main** slot of the default page, add an order confirmation module.</span></span>
1. <span data-ttu-id="0bd13-126">Lägg till en rekommendationsmodul i orderbekräftelsemodulen.</span><span class="sxs-lookup"><span data-stu-id="0bd13-126">In the order confirmation module, add a recommendations module.</span></span>
1. <span data-ttu-id="0bd13-127">Spara och förhandsgranska mallen.</span><span class="sxs-lookup"><span data-stu-id="0bd13-127">Save and preview the template.</span></span> <span data-ttu-id="0bd13-128">Modulen för orderbekräftelse ska inte återges eftersom den kräver en kontext för orderbekräftelsenumret.</span><span class="sxs-lookup"><span data-stu-id="0bd13-128">The order confirmation module should not be rendered, because it requires the context of the order confirmation number.</span></span>
1. <span data-ttu-id="0bd13-129">Checka in mallen och publicera den.</span><span class="sxs-lookup"><span data-stu-id="0bd13-129">Check in the template, and publish it.</span></span>
1. <span data-ttu-id="0bd13-130">Använd den mall för orderbekräftelse som du just skapade för att skapa en sida med namnet **sida för orderbekräftelse**.</span><span class="sxs-lookup"><span data-stu-id="0bd13-130">Use the order confirmation template that you just created to create a page that is named **order confirmation page**.</span></span>
1. <span data-ttu-id="0bd13-131">Lägg till standardsidan i siddispositionen.</span><span class="sxs-lookup"><span data-stu-id="0bd13-131">Add the default page to the page outline.</span></span>
1. <span data-ttu-id="0bd13-132">Lägg till platsen **rubrik**, lägg till ett rubrikavsnitt.</span><span class="sxs-lookup"><span data-stu-id="0bd13-132">In the **Header** slot, add a header fragment.</span></span>
1. <span data-ttu-id="0bd13-133">Lägg till platsen **sidfot**, lägg till ett sidfotavsnitt.</span><span class="sxs-lookup"><span data-stu-id="0bd13-133">In the **Footer** slot, add a footer fragment.</span></span>
1. <span data-ttu-id="0bd13-134">På platsen **Huvud**, lägg till orderbekräftelsemodul.</span><span class="sxs-lookup"><span data-stu-id="0bd13-134">In the **Main** slot, add an order confirmation module.</span></span>
1. <span data-ttu-id="0bd13-135">I egenskapsfönstret för orderbekräftelsemodulen, lägg till **Orderbekräftelse**.</span><span class="sxs-lookup"><span data-stu-id="0bd13-135">In the property pane of the order confirmation module, add the heading **Order confirmation**.</span></span>
1. <span data-ttu-id="0bd13-136">Lägg till en rekommendationsmodul under orderbekräftelsesmodulen och konfigurera den så att den använder inställningarna **Ny** och **Bästsäljande**.</span><span class="sxs-lookup"><span data-stu-id="0bd13-136">Below the order confirmation module, add a recommendations module, and configure it so that it uses the **New** and **Best Selling** settings.</span></span>
1. <span data-ttu-id="0bd13-137">Spara och förhandsgranska sidan, checka in den och publicera den.</span><span class="sxs-lookup"><span data-stu-id="0bd13-137">Save and preview the page, check it in, and publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0bd13-138">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="0bd13-138">Additional resources</span></span>

[<span data-ttu-id="0bd13-139">Översikt över startpaket</span><span class="sxs-lookup"><span data-stu-id="0bd13-139">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="0bd13-140">Behållaremodul</span><span class="sxs-lookup"><span data-stu-id="0bd13-140">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="0bd13-141">Köp en boxmodul</span><span class="sxs-lookup"><span data-stu-id="0bd13-141">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="0bd13-142">Vagnmodul</span><span class="sxs-lookup"><span data-stu-id="0bd13-142">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="0bd13-143">Kassamodul</span><span class="sxs-lookup"><span data-stu-id="0bd13-143">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="0bd13-144">Rubrikmodul</span><span class="sxs-lookup"><span data-stu-id="0bd13-144">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="0bd13-145">Sidfotmodul</span><span class="sxs-lookup"><span data-stu-id="0bd13-145">Footer module</span></span>](author-footer-module.md)
