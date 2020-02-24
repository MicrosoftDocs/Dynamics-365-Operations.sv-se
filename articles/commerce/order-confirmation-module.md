---
title: Orderinformationsmodul
description: Det här avsnittet handlar om orderinformationsmoduler och beskriver hur du använder dem i Microsoft Dynamics 365 Commerce.
author: anupamar
manager: annbe
ms.date: 01/23/2020
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
ms.openlocfilehash: cb09a0b6ce1e48707f96021e9fad0006d9c1c55c
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/05/2020
ms.locfileid: "3026027"
---
# <a name="order-details-module"></a><span data-ttu-id="d91f0-103">Orderinformationsmodul</span><span class="sxs-lookup"><span data-stu-id="d91f0-103">Order details module</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="d91f0-104">Det här avsnittet handlar om orderinformationsmoduler och beskriver hur du använder dem i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="d91f0-104">This topic covers order details modules and describes how to use them in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="d91f0-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="d91f0-105">Overview</span></span>

<span data-ttu-id="d91f0-106">Orderinformationsmodul används för att visa bekräftelseinformationen när en order har placerats.</span><span class="sxs-lookup"><span data-stu-id="d91f0-106">The order details module is used to show order confirmation details after an order has been placed.</span></span> <span data-ttu-id="d91f0-107">Det visar order bekräftelse-ID, orderns kontaktinformation och annan orderinformation, till exempel de artiklar som har köpts, betalningsinformation och leveransmetoden.</span><span class="sxs-lookup"><span data-stu-id="d91f0-107">It shows the order confirmation ID, order contact information, and other order details, such as the items that were purchased, payment information, and the shipping method.</span></span>

## <a name="order-confirmation-module-properties"></a><span data-ttu-id="d91f0-108">Egenskaper för orderbekräftelsemodul</span><span class="sxs-lookup"><span data-stu-id="d91f0-108">Order confirmation module properties</span></span>

| <span data-ttu-id="d91f0-109">Egenskapsnamn</span><span class="sxs-lookup"><span data-stu-id="d91f0-109">Property name</span></span>  | <span data-ttu-id="d91f0-110">Värden</span><span class="sxs-lookup"><span data-stu-id="d91f0-110">Values</span></span> | <span data-ttu-id="d91f0-111">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="d91f0-111">Description</span></span> |
|----------------|--------|-------------|
| <span data-ttu-id="d91f0-112">Rubrik</span><span class="sxs-lookup"><span data-stu-id="d91f0-112">Heading</span></span>        | <span data-ttu-id="d91f0-113">Rubriktext och rubriktagg (**H1**, **H2**, **H3**, **H4**, **H5** eller **H6**)</span><span class="sxs-lookup"><span data-stu-id="d91f0-113">Heading text and heading tag (**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**)</span></span> | <span data-ttu-id="d91f0-114">Orderbekräftelsemodulen kan ha en rubrik.</span><span class="sxs-lookup"><span data-stu-id="d91f0-114">The order confirmation module can have a heading.</span></span> <span data-ttu-id="d91f0-115">Som standard används rubriktaggen **H2** för rubriken.</span><span class="sxs-lookup"><span data-stu-id="d91f0-115">By default, the **H2** heading tag is used for the heading.</span></span> <span data-ttu-id="d91f0-116">Taggen kan emellertid ändras så att den uppfyller tillgänglighetskraven.</span><span class="sxs-lookup"><span data-stu-id="d91f0-116">However, the tag can be changed to meet accessibility requirements.</span></span> |
| <span data-ttu-id="d91f0-117">Kontaktnummer</span><span class="sxs-lookup"><span data-stu-id="d91f0-117">Contact number</span></span> | <span data-ttu-id="d91f0-118">Text</span><span class="sxs-lookup"><span data-stu-id="d91f0-118">Text</span></span> | <span data-ttu-id="d91f0-119">Ett kontaktnummer kan anges för frågor som är relaterade till order.</span><span class="sxs-lookup"><span data-stu-id="d91f0-119">A contact number can be provided for order-related questions.</span></span> |

## <a name="modules-that-can-be-used-on-an-order-details-page"></a><span data-ttu-id="d91f0-120">Moduler som kan användas på en sida för orderinformation</span><span class="sxs-lookup"><span data-stu-id="d91f0-120">Modules that can be used on an order details page</span></span>

<span data-ttu-id="d91f0-121">När du skapar en sida för orderinformation kan du lägga till andra relevanta moduler utöver orderinformationsmodulen.</span><span class="sxs-lookup"><span data-stu-id="d91f0-121">When you create an order details page, you can add other relevant modules in addition to the order details module.</span></span> <span data-ttu-id="d91f0-122">Nedan följer några exempel:</span><span class="sxs-lookup"><span data-stu-id="d91f0-122">Here are some examples:</span></span>

- <span data-ttu-id="d91f0-123">**Rekommendationsmodul** – modulen rekommendationer kan läggs till på sidan för orderinformation för att föreslå andra produkter till kunden.</span><span class="sxs-lookup"><span data-stu-id="d91f0-123">**Recommendations module** – The recommendations module can be added to the order details page to suggest other products to the customer.</span></span>
- <span data-ttu-id="d91f0-124">**Marknadsföringsmoduler** – valfri marknadsföringsmodul kan läggas till på sidan orderinformation om du vill visa marknadsföringsinnehåll.</span><span class="sxs-lookup"><span data-stu-id="d91f0-124">**Marketing modules** – Any marketing module can be added to the order details page to show marketing content.</span></span>

## <a name="create-an-order-details-page-module"></a><span data-ttu-id="d91f0-125">Skapa en sida för orderinformationsmodul</span><span class="sxs-lookup"><span data-stu-id="d91f0-125">Create an order details page module</span></span>

1. <span data-ttu-id="d91f0-126">Skapa en sidmall som har namnet **orderinformationsmall**.</span><span class="sxs-lookup"><span data-stu-id="d91f0-126">Create a page template that is named **Order details template**.</span></span>
1. <span data-ttu-id="d91f0-127">Lägg till platsen **Huvud** på standardsida, lägg till orderinformationsmodul.</span><span class="sxs-lookup"><span data-stu-id="d91f0-127">In the **Main** slot of the default page, add an order details module.</span></span>
1. <span data-ttu-id="d91f0-128">Lägg till en rekommendationsmodul i orderinformationsmodulen.</span><span class="sxs-lookup"><span data-stu-id="d91f0-128">In the order details module, add a recommendations module.</span></span>
1. <span data-ttu-id="d91f0-129">Spara och förhandsgranska mallen.</span><span class="sxs-lookup"><span data-stu-id="d91f0-129">Save and preview the template.</span></span> <span data-ttu-id="d91f0-130">Orderinformationsmodulen kommer inte återges eftersom den kräver en kontext för orderbekräftelsenumret.</span><span class="sxs-lookup"><span data-stu-id="d91f0-130">The order details module won't be rendered, because it requires the context of the order confirmation number.</span></span>
1. <span data-ttu-id="d91f0-131">Avsluta redigeringen i mallen och publicera den.</span><span class="sxs-lookup"><span data-stu-id="d91f0-131">Finish editing the template, and publish it.</span></span>
1. <span data-ttu-id="d91f0-132">Använd den orderinformationsmall som du just skapade för att skapa en sida med namnet **sida för orderinformation**.</span><span class="sxs-lookup"><span data-stu-id="d91f0-132">Use the order details template that you just created to create a page that is named **order details page**.</span></span>
1. <span data-ttu-id="d91f0-133">Lägg till standardsidan i siddispositionen.</span><span class="sxs-lookup"><span data-stu-id="d91f0-133">Add the default page to the page outline.</span></span>
1. <span data-ttu-id="d91f0-134">Lägg till platsen **rubrik**, lägg till ett rubrikavsnitt.</span><span class="sxs-lookup"><span data-stu-id="d91f0-134">In the **Header** slot, add a header fragment.</span></span>
1. <span data-ttu-id="d91f0-135">Lägg till platsen **sidfot**, lägg till ett sidfotavsnitt.</span><span class="sxs-lookup"><span data-stu-id="d91f0-135">In the **Footer** slot, add a footer fragment.</span></span>
1. <span data-ttu-id="d91f0-136">På platsen **Huvud**, lägg till orderinformationsmodul.</span><span class="sxs-lookup"><span data-stu-id="d91f0-136">In the **Main** slot, add an order details module.</span></span>
1. <span data-ttu-id="d91f0-137">I egenskapsfönstret för orderinformationsmodulen, lägg till **orderinformation**.</span><span class="sxs-lookup"><span data-stu-id="d91f0-137">In the property pane for the order details module, add the heading **Order details**.</span></span>
1. <span data-ttu-id="d91f0-138">Lägg till en rekommendationsmodul under orderinformationsmodulen och konfigurera den så att den använder inställningarna **Ny** och **Bästsäljande**.</span><span class="sxs-lookup"><span data-stu-id="d91f0-138">Below the order details module, add a recommendations module, and configure it so that it uses the **New** and **Best Selling** settings.</span></span>
1. <span data-ttu-id="d91f0-139">Spara och förhandsgranska sidan.</span><span class="sxs-lookup"><span data-stu-id="d91f0-139">Save and preview the page.</span></span>
1. <span data-ttu-id="d91f0-140">Avsluta redigeringen av sidan och publicera den.</span><span class="sxs-lookup"><span data-stu-id="d91f0-140">Finish editing the page, and publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d91f0-141">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="d91f0-141">Additional resources</span></span>

[<span data-ttu-id="d91f0-142">Startpaket – översikt</span><span class="sxs-lookup"><span data-stu-id="d91f0-142">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="d91f0-143">Behållaremodul</span><span class="sxs-lookup"><span data-stu-id="d91f0-143">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="d91f0-144">Köp en boxmodul</span><span class="sxs-lookup"><span data-stu-id="d91f0-144">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="d91f0-145">Vagnmodul</span><span class="sxs-lookup"><span data-stu-id="d91f0-145">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="d91f0-146">Kassamodul</span><span class="sxs-lookup"><span data-stu-id="d91f0-146">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="d91f0-147">Rubrikmodul</span><span class="sxs-lookup"><span data-stu-id="d91f0-147">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="d91f0-148">Sidfotmodul</span><span class="sxs-lookup"><span data-stu-id="d91f0-148">Footer module</span></span>](author-footer-module.md)
