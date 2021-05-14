---
title: Presentkortsmodul
description: Det här avsnittet handlar om presentkortsmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 04/29/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 8db7e597241f1fd552f6b960c2b57b0ba83da949
ms.sourcegitcommit: efde05c758b2e02960760d875569d780d77d5550
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/29/2021
ms.locfileid: "5962773"
---
# <a name="gift-card-module"></a><span data-ttu-id="e18ef-103">Presentkortsmodul</span><span class="sxs-lookup"><span data-stu-id="e18ef-103">Gift card module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="e18ef-104">Det här avsnittet handlar om presentkortsmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="e18ef-104">This topic covers gift card modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="e18ef-105">Presentkortmoduler är en vanlig typ av betalningsmoduler för att acceptera presentkort, en vanlig betalningsmetod för näthandelstransaktioner.</span><span class="sxs-lookup"><span data-stu-id="e18ef-105">Gift card modules can be used in checkout modules to accept gift cards, a common form of payment used for e-Commerce transactions.</span></span> <span data-ttu-id="e18ef-106">Presentkortsmodulen kan användas med Dynamics 365, SVS, och Givex presentkortskort.</span><span class="sxs-lookup"><span data-stu-id="e18ef-106">The gift card module supports Dynamics 365, SVS, and Givex gift cards.</span></span> <span data-ttu-id="e18ef-107">SVS och Givex presentkort löses in via Adyen betalningsförmedlaren.</span><span class="sxs-lookup"><span data-stu-id="e18ef-107">SVS and Givex gift cards are redeemed via the Adyen payment provider.</span></span> <span data-ttu-id="e18ef-108">Mer information om stöd för externa presentkort, t.ex. SVS och Givex, se [Stöd för externa presentkort](./dev-itpro/gift-card.md).</span><span class="sxs-lookup"><span data-stu-id="e18ef-108">For more information about support for external gift cards such as SVS and Givex, see [Support for external gift cards](./dev-itpro/gift-card.md).</span></span>

> [!NOTE]
> <span data-ttu-id="e18ef-109">Stöd för att lösa in SVS och Givex presentkort under kassaflödet är tillgängligt i Dynamics 365 Commerce 10.0.11-versionen.</span><span class="sxs-lookup"><span data-stu-id="e18ef-109">Support for redeeming SVS and Givex gift cards during checkout flow is available in the Dynamics 365 Commerce 10.0.11 release.</span></span> 

<span data-ttu-id="e18ef-110">Det finns två tillgängliga presentkortmoduler:</span><span class="sxs-lookup"><span data-stu-id="e18ef-110">There are two gift card modules available:</span></span>

- <span data-ttu-id="e18ef-111">**Presentkort** – Denna modul kan användas på en betalningssida för att lösa in ett presentkort som betalningsmedel.</span><span class="sxs-lookup"><span data-stu-id="e18ef-111">**Gift card** – This module can be used on a checkout page to redeem a gift card as tender.</span></span> 
- <span data-ttu-id="e18ef-112">**Kontroll av presentkortssaldo** – Denna modul kan användas på alla sidor för att kontrollera saldot på ett presentkort.</span><span class="sxs-lookup"><span data-stu-id="e18ef-112">**Gift card balance check** – This module can be used on any page to check the balance on a gift card.</span></span> <span data-ttu-id="e18ef-113">Den här modulen är tillgänglig i Commerce version 10.0.14 och senare.</span><span class="sxs-lookup"><span data-stu-id="e18ef-113">This module is available in Commerce release 10.0.14 and later.</span></span>

> [!NOTE]
> <span data-ttu-id="e18ef-114">Stödet för modulen Kontroll av presentkortssaldo är tillgänglig i Dynamics 365 Commerce 10.0.14-versionen.</span><span class="sxs-lookup"><span data-stu-id="e18ef-114">Support for the gift card balance check module is available in the Dynamics 365 Commerce 10.0.14 release.</span></span>

<span data-ttu-id="e18ef-115">Följande bild visar ett exempel på en presentkortmodul på en kassasida.</span><span class="sxs-lookup"><span data-stu-id="e18ef-115">The following image shows an example of a gift card module on a checkout page.</span></span>

![Exempel på en presentkortsmodul](./media/ecommerce-giftcard.PNG)

## <a name="module-properties"></a><span data-ttu-id="e18ef-117">Modulegenskaper</span><span class="sxs-lookup"><span data-stu-id="e18ef-117">Module properties</span></span>

- <span data-ttu-id="e18ef-118">**Visa ytterligare fält** – Denna egenskap definierar vilka fält som ska visas för presentkort utöver presentkortsnumret, som alltid visas som standard.</span><span class="sxs-lookup"><span data-stu-id="e18ef-118">**Show additional fields** – This property defines what fields should be displayed for gift cards in addition to the gift card number, which is always displayed by default.</span></span> <span data-ttu-id="e18ef-119">Vissa presentkort stöder t.ex. ett personligt ID-nummer (PIN-kod) och andra support visar en PIN-kod och ett förfallodatum.</span><span class="sxs-lookup"><span data-stu-id="e18ef-119">For example, some gift cards support displaying a personal identification number (PIN), and others support displaying a PIN and expiration date.</span></span> <span data-ttu-id="e18ef-120">Alternativt kan den här egenskapen anges till "ingen", vilket bara visar presentkortsnumret och inga ytterligare fält.</span><span class="sxs-lookup"><span data-stu-id="e18ef-120">Alternatively, this property could be set to "None", which would only display the gift card number and no additional fields.</span></span>

<span data-ttu-id="e18ef-121">Värden som stöds:</span><span class="sxs-lookup"><span data-stu-id="e18ef-121">Supported values:</span></span>
-   <span data-ttu-id="e18ef-122">PIN-kod</span><span class="sxs-lookup"><span data-stu-id="e18ef-122">PIN</span></span>
-   <span data-ttu-id="e18ef-123">Utgångsdatum</span><span class="sxs-lookup"><span data-stu-id="e18ef-123">Expiration date</span></span>
-   <span data-ttu-id="e18ef-124">PIN och utgångsdatum</span><span class="sxs-lookup"><span data-stu-id="e18ef-124">PIN and expiration date</span></span> 
-   <span data-ttu-id="e18ef-125">None</span><span class="sxs-lookup"><span data-stu-id="e18ef-125">None</span></span>

## <a name="site-settings-for-gift-card-modules"></a><span data-ttu-id="e18ef-126">Platsinställningar för presentkortsmoduler</span><span class="sxs-lookup"><span data-stu-id="e18ef-126">Site settings for gift card modules</span></span>

<span data-ttu-id="e18ef-127">I Commerce webbplatsskaparen under **webbplatsinställnings \> tillägg**, finns en presentkorts inställning som kallas **presentkortstyp som stöds**.</span><span class="sxs-lookup"><span data-stu-id="e18ef-127">In Commerce site builder under **Site Settings \> Extensions**, there is a gift card module setting called **Supported gift card type**.</span></span> <span data-ttu-id="e18ef-128">Den här inställningen har stöd för tre värden:</span><span class="sxs-lookup"><span data-stu-id="e18ef-128">This setting supports three values:</span></span>
- <span data-ttu-id="e18ef-129">**Dynamics 365-presentkort** – När den här inställningen används tillåter presentkortsmodulen bara inlösen av Dynamics 365-presentkort.</span><span class="sxs-lookup"><span data-stu-id="e18ef-129">**Dynamics 365 gift card** – When this setting is applied, the gift card module only allows the redemption of Dynamics 365 gift cards.</span></span> <span data-ttu-id="e18ef-130">Den här inställningen stöds endast för inloggade användare på webbplatsen för näthandel.</span><span class="sxs-lookup"><span data-stu-id="e18ef-130">This setting is only supported for signed-in users on the e-Commerce site.</span></span>
- <span data-ttu-id="e18ef-131">**SVS- och Givex-presentkort** – När den här inställningen används tillåter presentkortsmodulen bara inlösen av SVS- och Givex-presentkort.</span><span class="sxs-lookup"><span data-stu-id="e18ef-131">**SVS and Givex gift cards** – When this setting is applied, the gift card module only allows the redemption of Givex and SVS gift cards.</span></span> <span data-ttu-id="e18ef-132">Den här inställningen stöds för inloggade anonyma användare på webbplatsen för näthandel.</span><span class="sxs-lookup"><span data-stu-id="e18ef-132">This setting is supported for signed-in and anonymous users on the e-Commerce site.</span></span>
- <span data-ttu-id="e18ef-133">**Dynamics 365-, SVS- och Givex-presentkort** – När den här inställningen används tillåter presentkortet inlösen av Dynamics 365-, Givex- och SVS-presentkort.</span><span class="sxs-lookup"><span data-stu-id="e18ef-133">**Dynamics 365, SVS, and Givex gift cards** – When this setting is applied, the gift card module allows the redemption of Dynamics 365, Givex, and SVS gift cards.</span></span> <span data-ttu-id="e18ef-134">Den här inställningen stöds endast för inloggade användare på webbplatsen för näthandel.</span><span class="sxs-lookup"><span data-stu-id="e18ef-134">This setting is only supported for signed-in users on the e-Commerce site.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e18ef-135">Dessa inställningar är tillgängliga i Dynamics 365 Commerce 10.0.11-versionen och krävs endast om du behöver stöd för SVS eller Givex presentkort.</span><span class="sxs-lookup"><span data-stu-id="e18ef-135">These settings are available in the Dynamics 365 Commerce 10.0.11 release and are required only if you need support for SVS or Givex gift cards.</span></span> <span data-ttu-id="e18ef-136">Om du uppdaterar från en äldre version av Dynamics 365 Commerce måste du uppdatera filen appsettings.json manuellt.</span><span class="sxs-lookup"><span data-stu-id="e18ef-136">If you are updating from an older version of Dynamics 365 Commerce, you must manually update the appsettings.json file.</span></span> <span data-ttu-id="e18ef-137">Information om hur du uppdaterar filen appsettings.json finns i [SDK- och modulens biblioteksuppdateringar](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).</span><span class="sxs-lookup"><span data-stu-id="e18ef-137">For instructions on updating the appsettings.json file, see [SDK and module library updates](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).</span></span> 

## <a name="extend-internal-gift-cards-for-use-in-e-commerce-storefronts"></a><span data-ttu-id="e18ef-138">Utöka interna presentkort för användning i näthandelsbutik</span><span class="sxs-lookup"><span data-stu-id="e18ef-138">Extend internal gift cards for use in e-commerce storefronts</span></span>

<span data-ttu-id="e18ef-139">Som standard är interna presentkort inte optimerade för användning i näthandelsskyltfönster.</span><span class="sxs-lookup"><span data-stu-id="e18ef-139">By default, internal gift cards aren't optimized for use in e-commerce storefronts.</span></span> <span data-ttu-id="e18ef-140">Innan du tillåter att interna presentkort används som betalning bör du därför konfigurera dem med tillägg som gör dem säkrare.</span><span class="sxs-lookup"><span data-stu-id="e18ef-140">Therefore, before you allow internal gift cards to be used for payment, you should configure them with extensions that help make them more secure.</span></span> <span data-ttu-id="e18ef-141">Här följer de områden med presentkort som du bör utöka innan du tillåter att interna presentkort används i produktionen:</span><span class="sxs-lookup"><span data-stu-id="e18ef-141">Here are the gift card areas that you should extend before you allow internal gift cards to be used in production:</span></span>

- <span data-ttu-id="e18ef-142">**Presentkortsnummer** – Nummerserier används för att generera presentkortsnummer för interna presentkort.</span><span class="sxs-lookup"><span data-stu-id="e18ef-142">**Gift card number** – Number sequences are used to generate gift card numbers for internal gift cards.</span></span> <span data-ttu-id="e18ef-143">Eftersom nummerserier enkelt kan förutsägas bör du utöka genereringen av presentkortsnummer så att slumpmässiga, kryptografiskt säkra strängar används för de presentkortsnummer som utfärdas.</span><span class="sxs-lookup"><span data-stu-id="e18ef-143">Because number sequences can easily be predicted, you should extend the generation of gift card numbers so that random, cryptographically secure strings are used for the gift card numbers that are issued.</span></span>
- <span data-ttu-id="e18ef-144">**GetBalance** – API:t **GetBalance** används för att slå upp presentkortssaldon.</span><span class="sxs-lookup"><span data-stu-id="e18ef-144">**GetBalance** – The **GetBalance** API is used to look up gift card balances.</span></span> <span data-ttu-id="e18ef-145">Som standard är denna API offentlig.</span><span class="sxs-lookup"><span data-stu-id="e18ef-145">By default, this API public.</span></span> <span data-ttu-id="e18ef-146">Om en PIN-kod inte krävs för att slå upp presentkortssaldon finns det en risk för att råstyrkeattacker kan använda API:t **GetBalande** för att söka efter presentkortsnummer som har saldon.</span><span class="sxs-lookup"><span data-stu-id="e18ef-146">If a PIN isn't required to look up gift card balances, there is a risk that brute force attacks could use the **GetBalance** API to try to look up gift card numbers that have balances.</span></span> <span data-ttu-id="e18ef-147">Genom att implementera både PIN-krav för interna presentkort och API-begränsning kan du minska risken.</span><span class="sxs-lookup"><span data-stu-id="e18ef-147">By implementing both PIN requirements for internal gift cards and API throttling, you can help mitigate the risk.</span></span>
- <span data-ttu-id="e18ef-148">**PIN** – Som standard har interna presentkort inte stöd för PINs.</span><span class="sxs-lookup"><span data-stu-id="e18ef-148">**PIN** – By default, internal gift cards don't support PINs.</span></span> <span data-ttu-id="e18ef-149">Du bör utöka interna presentkort så att det krävs en PIN-kod för att slå upp saldon.</span><span class="sxs-lookup"><span data-stu-id="e18ef-149">You should extend internal gift cards so that a PIN is required to look up balances.</span></span> <span data-ttu-id="e18ef-150">Den här funktionen kan även användas för att låsa presentkort efter på varandra följande felaktiga försök att ange PIN-koden.</span><span class="sxs-lookup"><span data-stu-id="e18ef-150">This functionality can also be used to lock gift cards after consecutive incorrect attempts to enter the PIN.</span></span>

## <a name="enable-gift-card-payments-for-guest-checkout"></a><span data-ttu-id="e18ef-151">Aktivera presentkortsbetalningar för gästkassa</span><span class="sxs-lookup"><span data-stu-id="e18ef-151">Enable gift card payments for guest checkout</span></span>

<span data-ttu-id="e18ef-152">Som standard aktiveras inte presentkortsbetalningar för gästkassa (anonymt).</span><span class="sxs-lookup"><span data-stu-id="e18ef-152">By default, gift card payments aren't enabled for guest (anonymous) checkout.</span></span> <span data-ttu-id="e18ef-153">För att aktivera dem följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="e18ef-153">To enable them, follow these steps.</span></span>

1. <span data-ttu-id="e18ef-154">I Commerce-administrationen går du till **Retail och Commerce \> Kanalinställningar \> Kassainställningar \> Kassa \> Kassafunktioner**.</span><span class="sxs-lookup"><span data-stu-id="e18ef-154">In Commerce headquarters, go to **Retail and Commerce \> Channel setup \> POS setup \> POS \> POS Operations**.</span></span>
1. <span data-ttu-id="e18ef-155">Markera och håll (eller högerklicka) på rutnätets rubrik och välj sedan **Infoga kolumner**.</span><span class="sxs-lookup"><span data-stu-id="e18ef-155">Select and hold (or right-click) the header of the grid, and then select **Insert columns**.</span></span>
1. <span data-ttu-id="e18ef-156">I dialogrutan **Infoga kolumner** väljer du kryssrutan **AllowAnonymousAccess**.</span><span class="sxs-lookup"><span data-stu-id="e18ef-156">In the **Insert columns** dialog box, select the **AllowAnonymousAccess** check box.</span></span>
1. <span data-ttu-id="e18ef-157">Välj **Uppdatera**.</span><span class="sxs-lookup"><span data-stu-id="e18ef-157">Select **Update**.</span></span>
1. <span data-ttu-id="e18ef-158">För funktionerna **520** (presentkortssaldo) och **214** anger du värdet för **AllowAnonymousAccess** som **1**.</span><span class="sxs-lookup"><span data-stu-id="e18ef-158">For operations **520** (Gift card balance) and **214**, set the **AllowAnonymousAccess** value to **1**.</span></span>
1. <span data-ttu-id="e18ef-159">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="e18ef-159">Select **Save**.</span></span>
1. <span data-ttu-id="e18ef-160">Kör schemaläggningsjobbet **1090** för att synkronisera ändringar i kanaldatabasen.</span><span class="sxs-lookup"><span data-stu-id="e18ef-160">Run the **1090** scheduler job to sync changes to the channel database.</span></span> 

## <a name="add-a-gift-card-module-to-a-page"></a><span data-ttu-id="e18ef-161">Lägg till presentkortmodulen på en ny sida</span><span class="sxs-lookup"><span data-stu-id="e18ef-161">Add a gift card module to a page</span></span>

<span data-ttu-id="e18ef-162">Instruktioner om hur du lägger till en presentkortsmodul på en betalningssida och anger de obligatoriska egenskaperna finns i [betalningsmodulen](add-checkout-module.md).</span><span class="sxs-lookup"><span data-stu-id="e18ef-162">For instructions on how to add a gift card module to a checkout page and set the required properties, see [Checkout module](add-checkout-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e18ef-163">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="e18ef-163">Additional resources</span></span>

[<span data-ttu-id="e18ef-164">Kundvagnsmodul</span><span class="sxs-lookup"><span data-stu-id="e18ef-164">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="e18ef-165">Ikon för kundvagnsmodul</span><span class="sxs-lookup"><span data-stu-id="e18ef-165">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="e18ef-166">Kassamodul</span><span class="sxs-lookup"><span data-stu-id="e18ef-166">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="e18ef-167">Betalningsmodul</span><span class="sxs-lookup"><span data-stu-id="e18ef-167">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="e18ef-168">Modul för leveransadress</span><span class="sxs-lookup"><span data-stu-id="e18ef-168">Shipping address module</span></span>](ship-address-module.md)

[<span data-ttu-id="e18ef-169">Modul för leveransalternativ</span><span class="sxs-lookup"><span data-stu-id="e18ef-169">Delivery options module</span></span>](delivery-options-module.md)

[<span data-ttu-id="e18ef-170">Informationsmodul för upphämtning</span><span class="sxs-lookup"><span data-stu-id="e18ef-170">Pickup information module</span></span>](pickup-info-module.md)

[<span data-ttu-id="e18ef-171">Orderinformationsmodul</span><span class="sxs-lookup"><span data-stu-id="e18ef-171">Order details module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="e18ef-172">Stöd för externa presentkort</span><span class="sxs-lookup"><span data-stu-id="e18ef-172">Support for external gift cards</span></span>](./dev-itpro/gift-card.md)

[<span data-ttu-id="e18ef-173">Uppdateringar av SDK och modulbibliotek</span><span class="sxs-lookup"><span data-stu-id="e18ef-173">SDK and module library updates</span></span>](e-commerce-extensibility/sdk-updates.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
