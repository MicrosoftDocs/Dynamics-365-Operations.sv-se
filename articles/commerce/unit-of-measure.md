---
title: Använd inställningar för måttenhet
description: Det här avsnittet behandlar inställningar för måttenhet och beskriver hur du använder dem i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 7d338ba207c9a101f5e224ca66555b16a457bcbc
ms.sourcegitcommit: dc4898aa32f381620c517bf89c7856e693563ace
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/17/2021
ms.locfileid: "6271411"
---
# <a name="apply-unit-of-measure-settings"></a><span data-ttu-id="89692-103">Använd inställningar för måttenhet</span><span class="sxs-lookup"><span data-stu-id="89692-103">Apply unit of measure settings</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="89692-104">Det här avsnittet behandlar inställningar för måttenhet och beskriver hur du använder dem i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="89692-104">This topic covers unit of measure settings and describes how to apply them in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="89692-105">En produkt kan säljas i olika enheter, till exempel "varje", "par" och "dussin".</span><span class="sxs-lookup"><span data-stu-id="89692-105">A product can be sold in different units, such as "each," "pair," and "dozen."</span></span> <span data-ttu-id="89692-106">I Commerce-administrationen kan måttenheten för försäljning definieras för en produkt och visas på en näthandelsplats.</span><span class="sxs-lookup"><span data-stu-id="89692-106">In Commerce headquarters, the sell-by unit of measure can be defined for a product and shown on an e-commerce site.</span></span> <span data-ttu-id="89692-107">Om till exempel en återförsäljare säljer en produkt både enskilt och per dussin kan de tillgängliga måttenheterna visas tillsammans med annan produktinformation.</span><span class="sxs-lookup"><span data-stu-id="89692-107">For example, if a retailer sells a product both individually and in dozens, the available units of measure can be shown together with other product information.</span></span>

<span data-ttu-id="89692-108">I exemplet i följande illustration har måttenheten **ea** (varje) för försäljning angetts för en produkt i Commerce-administrationen.</span><span class="sxs-lookup"><span data-stu-id="89692-108">In the example in the following illustration, a sell-by unit of measure of **ea** (each) has been configured for a product in Commerce headquarters.</span></span>

![Exempel på en produkt som konfigurerats med en måttenhet i Commerce-administrationen](./media/Productunit-headquarters.PNG)

> [!NOTE]
> <span data-ttu-id="89692-110">Stöd för att tillämpa och visa måttenheten är tillgängligt i version 10.0.19 av Commerce.</span><span class="sxs-lookup"><span data-stu-id="89692-110">Support for applying and showing the unit of measure is available as of the Commerce version 10.0.19 release.</span></span>

## <a name="unit-of-measure-settings"></a><span data-ttu-id="89692-111">Inställningar för måttenhet</span><span class="sxs-lookup"><span data-stu-id="89692-111">Unit of measure settings</span></span>

<span data-ttu-id="89692-112">Visningsinställningarna för måttenheten definieras i Commerce-webbplatsbyggaren på **Webbplatsinställningar: \> Tillägg \> Visa måttenhet för produkter**.</span><span class="sxs-lookup"><span data-stu-id="89692-112">Unit of measure display settings are defined in Commerce site builder, at **Site settings \> Extensions \> Display unit of measure for products**.</span></span> <span data-ttu-id="89692-113">Det finns tre inställningar som stöds:</span><span class="sxs-lookup"><span data-stu-id="89692-113">There are three supported settings:</span></span>

- <span data-ttu-id="89692-114">**Visa inte** – När den här inställningen har valts visar näthandelsplatsen inte produktens måttenhet.</span><span class="sxs-lookup"><span data-stu-id="89692-114">**Do not display** – When this setting is selected, the e-commerce site won't show the unit of measure for the product.</span></span> <span data-ttu-id="89692-115">Detta beteende är standard.</span><span class="sxs-lookup"><span data-stu-id="89692-115">This behavior is the default behavior.</span></span>
- <span data-ttu-id="89692-116">**Visa i produktens inköpsupplevelse** – När den här inställningen har valts visas måttenheten i produktinformation, kundvagn, kassa, orderhistorik och orderinformationssidor.</span><span class="sxs-lookup"><span data-stu-id="89692-116">**Display in the product buying experience** – When this setting is selected, the unit of measure is shown on product details, cart, checkout, order history, and order details pages.</span></span>
- <span data-ttu-id="89692-117">**Visa i produktsöknings- och inköpsupplevelsen** – När den här inställningen har valts visas måttenheten på sidorna för produktköp och även i samband med sökupplevelsen för produkten.</span><span class="sxs-lookup"><span data-stu-id="89692-117">**Display in the product browsing and buying experience** – When this setting is selected, the unit of measure is shown on the product buying experience pages and also during the product browsing experience.</span></span> <span data-ttu-id="89692-118">Som en del av detta beteende visas måttenheter i sökresultat och moduler för produktsamling.</span><span class="sxs-lookup"><span data-stu-id="89692-118">As part of this behavior, units of measure are shown in search results and product collection modules.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="89692-119">Visningsinställningar för måttenhet är tillgängliga från och med version 10.0.19 av Commerce.</span><span class="sxs-lookup"><span data-stu-id="89692-119">Unit of measure display settings are available as of the Commerce version 10.0.19 release.</span></span> <span data-ttu-id="89692-120">Om du uppdaterar från en äldre version av Commerce måste du uppdatera filen appsettings.json manuellt.</span><span class="sxs-lookup"><span data-stu-id="89692-120">If you're updating from an older version of Commerce, you must manually update the appsettings.json file.</span></span> <span data-ttu-id="89692-121">För instruktioner, se [SDK- och modulbiblioteksuppdateringar](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).</span><span class="sxs-lookup"><span data-stu-id="89692-121">For instructions, see [SDK and module library updates](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).</span></span>

## <a name="modules-that-use-unit-of-measure-settings"></a><span data-ttu-id="89692-122">Moduler som använder inställningar för måttenhet</span><span class="sxs-lookup"><span data-stu-id="89692-122">Modules that use unit of measure settings</span></span>

<span data-ttu-id="89692-123">Moduler som använder måttenhetens inställningar inkluderar köprutan, listan, kundvagnen, kundvagnsikonen, sökresultatbehållare, produktsamling, kassa ut och moduler för orderinformation.</span><span class="sxs-lookup"><span data-stu-id="89692-123">Modules that use the unit of measure settings include the buy box, wishlist, cart, cart icon, search results container, product collection, checkout, and order details modules.</span></span>

<span data-ttu-id="89692-124">I exemplet i följande illustration visar en produktinformationssida (PDP) måttenheten (**ea**) för en produkt.</span><span class="sxs-lookup"><span data-stu-id="89692-124">In the example in the following illustration, a product details page (PDP) shows the unit of measure (**ea**) for a product.</span></span>

![Exempel på en PDP som visar måttenheten](./media/Productunit-PDP.png)

<span data-ttu-id="89692-126">I exemplet i följande illustration visar en produktsamlingsmodul måttenheten (**ea**) för en produkt.</span><span class="sxs-lookup"><span data-stu-id="89692-126">In the example in the following illustration, a product collection module shows the unit of measure (**ea**) for a product.</span></span>

![Exempel på en produktsamlingsmodul som visar måttenheten](./media/Productunit-productcollection.png)

## <a name="additional-resources"></a><span data-ttu-id="89692-128">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="89692-128">Additional resources</span></span>

[<span data-ttu-id="89692-129">Modulbibliotek – översikt</span><span class="sxs-lookup"><span data-stu-id="89692-129">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="89692-130">Kundvagnsmodul</span><span class="sxs-lookup"><span data-stu-id="89692-130">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="89692-131">Modul för inköpsruta</span><span class="sxs-lookup"><span data-stu-id="89692-131">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="89692-132">Sidor och moduler för kontohantering</span><span class="sxs-lookup"><span data-stu-id="89692-132">Account management pages and modules</span></span>](account-management.md)

[<span data-ttu-id="89692-133">Uppdateringar av SDK och modulbibliotek</span><span class="sxs-lookup"><span data-stu-id="89692-133">SDK and module library updates</span></span>](e-commerce-extensibility/sdk-updates.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
