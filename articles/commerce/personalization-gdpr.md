---
title: Avanmälan av anpassade rekommendationer
description: I det här avsnittet beskrivs hur du kan låta kunderna avanmäla si från anpassade rekommendationer i Microsoft Dynamics 365 Commerce.
author: bebeale
manager: AnnBe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: ''
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 6a64b45e1326673dd84c3c705491c9c100cdd069
ms.sourcegitcommit: 8028fbc5b9585e87d3331ea02577ff82ede090af
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/16/2020
ms.locfileid: "3817533"
---
# <a name="opt-out-of-personalized-recommendations"></a><span data-ttu-id="d8b2f-103">Avanmälan av anpassade rekommendationer</span><span class="sxs-lookup"><span data-stu-id="d8b2f-103">Opt out of personalized recommendations</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="d8b2f-104">I det här avsnittet beskrivs hur du kan låta kunderna avanmäla si från anpassade rekommendationer i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="d8b2f-104">This topic explains how you can let customers opt out of receiving personalized recommendations in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="d8b2f-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="d8b2f-105">Overview</span></span>

<span data-ttu-id="d8b2f-106">När kontot skapas konfigureras nya kunder automatiskt för att ta emot anpassade rekommendationer.</span><span class="sxs-lookup"><span data-stu-id="d8b2f-106">During account creation, new customers are automatically set up to receive personalized recommendations.</span></span> <span data-ttu-id="d8b2f-107">Med Dynamics 365 Commerce har olika sätt för återförsäljare att låta användarna välja att inte ta emot dessa rekommendationer och begränsa bearbetningen av personuppgifter.</span><span class="sxs-lookup"><span data-stu-id="d8b2f-107">However, Dynamics 365 Commerce provides various ways for retailers to let users opt out of receiving these recommendations and restrict the processing of their personal data.</span></span> <span data-ttu-id="d8b2f-108">Autentiserade användare som avanmäler sig från anpassade rekommendationer kommer omedelbart att sluta se anpassade listor.</span><span class="sxs-lookup"><span data-stu-id="d8b2f-108">Authenticated users who opt out of receiving personalized recommendations will immediately stop seeing personalized lists.</span></span> <span data-ttu-id="d8b2f-109">Dessutom kommer alla personliga data som samlas in för anpassning att tas bort från anpassade rekommendationsmodeller.</span><span class="sxs-lookup"><span data-stu-id="d8b2f-109">Additionally, all personal data that is collected for personalization will be removed from personalized recommendations models.</span></span>

<span data-ttu-id="d8b2f-110">Mer information om anpassade produktrekommendationer finns i [aktivera anpassade rekommendationer](personalized-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="d8b2f-110">For more information about personalized product recommendations, see [Enable personalized recommendations](personalized-recommendations.md).</span></span>

## <a name="ways-for-retailers-to-implement-an-opt-out-experience"></a><span data-ttu-id="d8b2f-111">Sätt för återförsäljare att använda en avanmälningsupplevelse</span><span class="sxs-lookup"><span data-stu-id="d8b2f-111">Ways for retailers to implement an opt-out experience</span></span>

<span data-ttu-id="d8b2f-112">Återförsäljare har tre sätt att använda en avanmälningsupplevelse.</span><span class="sxs-lookup"><span data-stu-id="d8b2f-112">Retailers have three ways to implement an opt-out experience.</span></span>

### <a name="opting-out-on-behalf-of-users"></a><span data-ttu-id="d8b2f-113">Avanmäla sig för användarnas räkning</span><span class="sxs-lookup"><span data-stu-id="d8b2f-113">Opting out on behalf of users</span></span>

<span data-ttu-id="d8b2f-114">I kontohantering i backoffice i Handel kan återförsäljare avanmäla sig för användarnas räkning.</span><span class="sxs-lookup"><span data-stu-id="d8b2f-114">In Account management in Commerce back office, retailers can opt out on behalf of users.</span></span>

1. <span data-ttu-id="d8b2f-115">På startsidan för backoffice söker du efter **alla kunder**.</span><span class="sxs-lookup"><span data-stu-id="d8b2f-115">From the back-office home page, search for **all customers**.</span></span>
1. <span data-ttu-id="d8b2f-116">Sök efter och välj en kund och välj sedan snabbfliken **butik**.</span><span class="sxs-lookup"><span data-stu-id="d8b2f-116">Search for and select a customer, and then select the **Retail** FastTab.</span></span>

    ![Snabbfliken Butik](./media/Disablepersonalizationpart1.png)

1. <span data-ttu-id="d8b2f-118">Under **sekretess** anger du alternativet **inaktivera anpassningar** till **ja**.</span><span class="sxs-lookup"><span data-stu-id="d8b2f-118">Under **Privacy**, set the **Disable personalization** option to **Yes**.</span></span>

    ![Sekretessinställningar](./media/Disablepersonalizationpart2.png)

1. <span data-ttu-id="d8b2f-120">Markera **Spara** och stäng sedan sidan.</span><span class="sxs-lookup"><span data-stu-id="d8b2f-120">Select **Save**, and close the page.</span></span>

### <a name="module-based-opt-out-experience"></a><span data-ttu-id="d8b2f-121">Modulbaserad avanmälningsupplevelse</span><span class="sxs-lookup"><span data-stu-id="d8b2f-121">Module-based opt-out experience</span></span>

<span data-ttu-id="d8b2f-122">Återförsäljare kan låta autentiserade användare välja att inte använda anpassade rekommendationer.</span><span class="sxs-lookup"><span data-stu-id="d8b2f-122">Retailers can let authenticated users opt out of personalized recommendations by themselves.</span></span> <span data-ttu-id="d8b2f-123">För att tillhandahålla den här avanmälningsupplevelsen lägger du till avanmälningsmodulen i profilsidor för kundkonton.</span><span class="sxs-lookup"><span data-stu-id="d8b2f-123">To provide this opt-out experience, add the user opt-out module to customer account profile pages.</span></span>

### <a name="custom-extensions"></a><span data-ttu-id="d8b2f-124">Anpassade tillägg</span><span class="sxs-lookup"><span data-stu-id="d8b2f-124">Custom extensions</span></span>

<span data-ttu-id="d8b2f-125">Återförsäljare kan skapa sina egna tillägg för att hantera användarnas avanmälningsfunktioner.</span><span class="sxs-lookup"><span data-stu-id="d8b2f-125">Retailers can create their own extensions to manage the opt-out experience for users.</span></span> <span data-ttu-id="d8b2f-126">Mer information finns i [anropa API:er för Butik](e-commerce-extensibility/call-retail-server-apis.md) och [Utbyggbarhet av onlinekanal](e-commerce-extensibility/overview.md).</span><span class="sxs-lookup"><span data-stu-id="d8b2f-126">For more information, see [Call Retail Server APIs](e-commerce-extensibility/call-retail-server-apis.md) and [Online channel extensibility](e-commerce-extensibility/overview.md).</span></span>

## <a name="obtain-a-digital-copy-of-personalized-recommendations-data-on-behalf-of-an-authenticated-user"></a><span data-ttu-id="d8b2f-127">Skaffa en digital kopia av dina anpassade rekommendationer, data för en autentiserad användares räkning</span><span class="sxs-lookup"><span data-stu-id="d8b2f-127">Obtain a digital copy of personalized recommendations data on behalf of an authenticated user</span></span>

<span data-ttu-id="d8b2f-128">Kunderna kanske vill skaffa en digital kopia av sina personliga data och också se en exporterad vy över sina rekommendationer.</span><span class="sxs-lookup"><span data-stu-id="d8b2f-128">Customers might want to obtain a digital copy of their personal data and also see an exported view of their recommendations results.</span></span> <span data-ttu-id="d8b2f-129">Om en kund begär denna information måste återförsäljaren skapa ett anpassat tillägg som anropar API i Retail Server och fråga efter fullständiga resultat från listan **Plocka åt dig** som baseras på kundens kund-ID.</span><span class="sxs-lookup"><span data-stu-id="d8b2f-129">If a customer requests this information, the retailer must create a customized extension that calls the Retail Server application programming interface (API) and queries for the full results from the **Picks for you** list, based on the customer's customer ID.</span></span> <span data-ttu-id="d8b2f-130">Resultaten kan sedan exporteras i CSV-format (kommaavgränsade värden) och delas med kunden.</span><span class="sxs-lookup"><span data-stu-id="d8b2f-130">The results can then be exported in comma-separated values (CSV) format and shared with the customer.</span></span>

<span data-ttu-id="d8b2f-131">Följande exempel visar hur en återförsäljare kan utföra uppgiften.</span><span class="sxs-lookup"><span data-stu-id="d8b2f-131">The following example shows how a retailer can accomplish this task.</span></span>

1. <span data-ttu-id="d8b2f-132">Återförsäljaren skapar ett anpassat tillägg för att hämta personliga rekommendationer för användarens räkning.</span><span class="sxs-lookup"><span data-stu-id="d8b2f-132">The retailer creates a custom extension to pull personal recommendations data on behalf of the user.</span></span> <span data-ttu-id="d8b2f-133">Information om hur du skapar moduler, klonar befintliga moduler, anropar API:er för Retail Server och anropar dataåtgärder finns i [Utbyggbarhet för onlinekanal](e-commerce-extensibility/overview.md).</span><span class="sxs-lookup"><span data-stu-id="d8b2f-133">For information about how to create modules, clone existing modules, call Retail Server APIs, and call data actions, see [Online channel extensibility](e-commerce-extensibility/overview.md).</span></span>
2. <span data-ttu-id="d8b2f-134">Det anpassade tillägget gör ett anrop till grundläggande dataåtgärder **skaffa rekommendationer** och skickar den nödvändiga informationen till den, baserat på kraven i listan.</span><span class="sxs-lookup"><span data-stu-id="d8b2f-134">The custom extension makes a call to the **get-recommendations** core data action and passes the required information to it, based on the requirements of the list.</span></span> <span data-ttu-id="d8b2f-135">Om du väljer listan **plockningar för dig** måste tillägget skicka rätt listnamn och kund-ID till dataåtgärden.</span><span class="sxs-lookup"><span data-stu-id="d8b2f-135">In the case of the **Picks for you** list, the extension must pass the correct list name and customer ID to the data action.</span></span>

    <span data-ttu-id="d8b2f-136">Ett sätt att skapa det anpassade tillägget är att klona den befintliga modulen för produktsamlingar som används för att returnera rekommendationer.</span><span class="sxs-lookup"><span data-stu-id="d8b2f-136">One way to create the custom extension is to clone the existing product collection module that is used to return recommendations results.</span></span> <span data-ttu-id="d8b2f-137">Genom att klona denna befintliga modul kan en återförsäljare ändra den befintliga koden och lägga till en ny knapp som exporterar rekommendationerna till en CSV-fil.</span><span class="sxs-lookup"><span data-stu-id="d8b2f-137">By cloning this existing module, a retailer can modify the existing code and add a new button that exports the recommendations results to a CSV file.</span></span> <span data-ttu-id="d8b2f-138">Mer information finns i [Klona en modul för modulbibliotek](e-commerce-extensibility/clone-starter-module.md) och [Produktsamlingsmoduler](product-collection-module-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d8b2f-138">For more information, see [Clone a module library module](e-commerce-extensibility/clone-starter-module.md) and [Product collection modules](product-collection-module-overview.md).</span></span>

    <span data-ttu-id="d8b2f-139">En fullständig vy av API-biblioteket för Retail Server finns i [API:er för Retail Server-kund och -konsument](dev-itpro/retail-server-customer-consumer-api.md).</span><span class="sxs-lookup"><span data-stu-id="d8b2f-139">For a full view of the Retail Server API library, see [Retail Server Customer and Consumer APIs](dev-itpro/retail-server-customer-consumer-api.md).</span></span>

3. <span data-ttu-id="d8b2f-140">När det anpassade tillägget har skapats kan återförsäljaren exportera en CSV-fil med alla rekommendationer, baserat på det unika kund-ID:t för den autentiserade användaren.</span><span class="sxs-lookup"><span data-stu-id="d8b2f-140">After the custom extension is created, the retailer can export a CSV file of all recommendations results, based on the unique customer ID of the authenticated user.</span></span>
4. <span data-ttu-id="d8b2f-141">Återförsäljaren kan dela den exporterade CSV-filen som innehåller den fullständiga anpassade listan över rekommenderade produkter med den autentiserade användaren.</span><span class="sxs-lookup"><span data-stu-id="d8b2f-141">The retailer can share the exported CSV file that contains the full personalized list of recommended products with the authenticated user.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d8b2f-142">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="d8b2f-142">Additional resources</span></span>

[<span data-ttu-id="d8b2f-143">Översikt av produktrekommendationer</span><span class="sxs-lookup"><span data-stu-id="d8b2f-143">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="d8b2f-144">Aktivera Azure Data Lake Storage i en Dynamics 365 Commerce-miljö</span><span class="sxs-lookup"><span data-stu-id="d8b2f-144">Enable Azure Data Lake Storage in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="d8b2f-145">Aktivera produktrekommendationer</span><span class="sxs-lookup"><span data-stu-id="d8b2f-145">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="d8b2f-146">Aktivera anpassade rekommendationer</span><span class="sxs-lookup"><span data-stu-id="d8b2f-146">Enable personalized recommendations</span></span>](personalized-recommendations.md)

[<span data-ttu-id="d8b2f-147">Aktivera rekommendationer för "köp liknande produkter"</span><span class="sxs-lookup"><span data-stu-id="d8b2f-147">Enable "shop similar looks" recommendations</span></span>](shop-similar-looks.md)

[<span data-ttu-id="d8b2f-148">Lägga till produktrekommendationer i kassan</span><span class="sxs-lookup"><span data-stu-id="d8b2f-148">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="d8b2f-149">Lägg till rekommendationer på transaktionsskärmen</span><span class="sxs-lookup"><span data-stu-id="d8b2f-149">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="d8b2f-150">Justera rekommendationsresultat från AI-ML</span><span class="sxs-lookup"><span data-stu-id="d8b2f-150">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="d8b2f-151">Skapa granskade rekommendationer manuellt</span><span class="sxs-lookup"><span data-stu-id="d8b2f-151">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="d8b2f-152">Skapa rekommendationer med demodata</span><span class="sxs-lookup"><span data-stu-id="d8b2f-152">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)

[<span data-ttu-id="d8b2f-153">Vanliga frågor om produktrekommendationer</span><span class="sxs-lookup"><span data-stu-id="d8b2f-153">Product recommendations FAQ</span></span>](faq-recommendations.md)
