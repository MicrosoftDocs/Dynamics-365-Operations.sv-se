---
title: Aktivera anpassade produktrekommendationer
description: I det här avsnittet beskrivs hur du gör anpassade produktrekommendationer tillgängliga för kunder i Microsoft Dynamics 365 Commerce.
author: bebeale
manager: AnnBe
ms.date: 08/18/2020
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
ms.openlocfilehash: 8a61ef0720839d371701f2f0a1fdec7e85a5feb7
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4415803"
---
# <a name="enable-personalized-recommendations"></a><span data-ttu-id="645d4-103">Aktivera anpassade rekommendationer</span><span class="sxs-lookup"><span data-stu-id="645d4-103">Enable personalized recommendations</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="645d4-104">I det här avsnittet beskrivs hur du gör anpassade produktrekommendationer tillgängliga för kunder i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="645d4-104">This topic describes how to make personalized product recommendations available for customers in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="645d4-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="645d4-105">Overview</span></span>

<span data-ttu-id="645d4-106">I Dynamics 365 Commerce kan återförsäljare göra anpassade produktrekommendationer (även kallade anpassningar) tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="645d4-106">In Dynamics 365 Commerce, retailers can make personalized product recommendations (also known as personalization) available.</span></span> <span data-ttu-id="645d4-107">På detta sätt kan personliga rekommendationer införlivas i kundupplevelsen online och i kassan (POS).</span><span class="sxs-lookup"><span data-stu-id="645d4-107">In this way, personalized recommendations can be incorporated into the customer experience online and at the point of sale (POS).</span></span> <span data-ttu-id="645d4-108">När anpassningsfunktionen är aktiverad kan systemet associera en användares inköps- och produktinformation för att skapa enskilda produktrekommendationer.</span><span class="sxs-lookup"><span data-stu-id="645d4-108">When the personalization functionality is turned on, the system can associate a user's purchase and product information to generate individualized product recommendations.</span></span>

## <a name="personalization-prerequisites"></a><span data-ttu-id="645d4-109">Anpassningskrav</span><span class="sxs-lookup"><span data-stu-id="645d4-109">Personalization prerequisites</span></span>

<span data-ttu-id="645d4-110">Innan du gör personliga produktrekommendationer tillgängliga för kunder bör du tänka på att produktrekommendationer bara stöds för användare av Handel som har migrerat deras lagring till Azure Data Lake Store.</span><span class="sxs-lookup"><span data-stu-id="645d4-110">Before you make personalized product recommendations available for customers, note that product recommendations are supported only for Commerce users who have migrated their storage to Azure Data Lake Store.</span></span> <span data-ttu-id="645d4-111">Innan kunderna får egna produktrekommendationer måste återförsäljare [aktivera produktrekommendationer](enable-product-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="645d4-111">Before customers can receive personalized product recommendations, retailers must [turn on product recommendations](enable-product-recommendations.md).</span></span>

> [!NOTE]
> <span data-ttu-id="645d4-112">Genom att aktivera produktrekommendationer aktiverar du också anpassningar.</span><span class="sxs-lookup"><span data-stu-id="645d4-112">By turning on product recommendations, you also turn on personalization.</span></span> <span data-ttu-id="645d4-113">Om du inaktiverar anpassningar stänger du emellertid inte av de andra typerna av produktrekommendationer.</span><span class="sxs-lookup"><span data-stu-id="645d4-113">However, if you turn off personalization, you don't turn off the other types of product recommendations.</span></span>

<span data-ttu-id="645d4-114">Mer information om produktrekommendationslistor finns i [produktrekommendationer - översikt](product-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="645d4-114">For more information about product recommendations, see the [Product recommendations overview](product-recommendations.md).</span></span>

## <a name="turn-on-personalization"></a><span data-ttu-id="645d4-115">Aktivera anpassning</span><span class="sxs-lookup"><span data-stu-id="645d4-115">Turn on personalization</span></span>

<span data-ttu-id="645d4-116">Så här aktiverar du anpassning.</span><span class="sxs-lookup"><span data-stu-id="645d4-116">To turn on personalization, follow these steps.</span></span>

1. <span data-ttu-id="645d4-117">Sök efter **funktionshantering** i Commerce Headquarters.</span><span class="sxs-lookup"><span data-stu-id="645d4-117">In Commerce headquarters, search for **Feature Management**.</span></span>
1. <span data-ttu-id="645d4-118">Välj **alla** om du vill visa en lista över tillgängliga funktioner.</span><span class="sxs-lookup"><span data-stu-id="645d4-118">Select **All** to see a list of available features.</span></span> 
1. <span data-ttu-id="645d4-119">Ange **rekommendationer** i sökrutan.</span><span class="sxs-lookup"><span data-stu-id="645d4-119">In the search box, enter **Recommendations**.</span></span>
1. <span data-ttu-id="645d4-120">Välj funktionen **Anpassade produktrekommendationer**.</span><span class="sxs-lookup"><span data-stu-id="645d4-120">Select the **Personalized product recommendations** feature.</span></span>
1. <span data-ttu-id="645d4-121">I egenskapsfönstret **Anpassade produktrekommendationer** välj **Aktivera nu**.</span><span class="sxs-lookup"><span data-stu-id="645d4-121">In the **Personalized product recommendations** properties pane, select **Enable now**.</span></span>

![Aktivera anpassning](./media/FeatureManagement_Personalized.PNG)

> [!NOTE]
> <span data-ttu-id="645d4-123">När du aktiverar anpassningar startas processen för generering av anpassade produktrekommendationslistor.</span><span class="sxs-lookup"><span data-stu-id="645d4-123">When you turn on personalization, the process of generating personalized product recommendation lists is started.</span></span> <span data-ttu-id="645d4-124">Det kan krävas upp till en dag innan dessa listor är tillgängliga och kan visas online och i kassan.</span><span class="sxs-lookup"><span data-stu-id="645d4-124">Up to one day might be required before these lists are available and visible online and at the POS.</span></span>

## <a name="personalized-lists"></a><span data-ttu-id="645d4-125">Anpassade listor</span><span class="sxs-lookup"><span data-stu-id="645d4-125">Personalized lists</span></span>

<span data-ttu-id="645d4-126">Förutom att göra anpassningar av befintliga datorgenererade listor, kan du med hjälp av rekommendationstjänsten anpassa produktidentifieringsupplevelsen både online och i kassan.</span><span class="sxs-lookup"><span data-stu-id="645d4-126">In addition to allowing for personalization of existing machine-generated lists, the recommendations service allows for personalization of the product discovery experience both online and at the POS.</span></span>

<span data-ttu-id="645d4-127">När anpassningen är aktiverad kan återförsäljare visa köparna anpassade "Val för dig"-listor online eller "rekommenderade kunder" i kassaterminaler.</span><span class="sxs-lookup"><span data-stu-id="645d4-127">After personalization is turned on, retailers can show shoppers personalized "Picks for you" lists online or "Recommended for customer" lists on POS terminals.</span></span> <span data-ttu-id="645d4-128">Dessutom kan återförsäljare lägga till anpassningar i befintliga produktrekommendationslistor och tillhandahålla allmän dataskyddsförordning (GDPR) avanmälningsupplevelse för autentiserade användare.</span><span class="sxs-lookup"><span data-stu-id="645d4-128">Additionally, retailers can apply personalization to existing product recommendation lists and provide General Data Protection Regulation (GDPR) opt-out experiences for authenticated users.</span></span> <span data-ttu-id="645d4-129">Om du inaktiverar anpassning inaktiveras även dessa funktioner.</span><span class="sxs-lookup"><span data-stu-id="645d4-129">If you turn off personalization, you also turn off these features.</span></span>

### <a name="online-picks-for-you-lists"></a><span data-ttu-id="645d4-130">"Val för dig"-listor online</span><span class="sxs-lookup"><span data-stu-id="645d4-130">Online "Picks for you" lists</span></span>

<span data-ttu-id="645d4-131">En Val för dig-lista är en lista med maskininlärning med artificiell intelligens (AI-ML) som visar en autentiserad användare en anpassad lista över föreslagna produkter.</span><span class="sxs-lookup"><span data-stu-id="645d4-131">A "Picks for you" list is an artificial intelligence-machine learning (AI-ML) list that shows an authenticated user a personalized list of suggested products.</span></span> <span data-ttu-id="645d4-132">Den här listan är baserad på användarens inköpshistorik i flera kanaler.</span><span class="sxs-lookup"><span data-stu-id="645d4-132">This list is based on the user's omnichannel purchase history.</span></span> <span data-ttu-id="645d4-133">Anpassade rekommendationer uppdateras dynamiskt när användaren gör fler inköp.</span><span class="sxs-lookup"><span data-stu-id="645d4-133">Personalized recommendations are dynamically updated as the user makes more purchases.</span></span> <span data-ttu-id="645d4-134">Den här typen av lista har också stöd för kategorifiltrering, så att återförsäljare kan visa de bästa valen baserat på navigationshierarkier.</span><span class="sxs-lookup"><span data-stu-id="645d4-134">This type of list also supports category filtering, so that retailers can show top picks, based on navigational hierarchies.</span></span>

<span data-ttu-id="645d4-135">Innan listan "Val för dig"-listan kan visas på alla näthandelssidor måste följande användarkrav uppfyllas:</span><span class="sxs-lookup"><span data-stu-id="645d4-135">Before the "Picks for you" list can appear on any e-Commerce page, the following user requirements must be met:</span></span>

- <span data-ttu-id="645d4-136">Användarna måste vara inloggade.</span><span class="sxs-lookup"><span data-stu-id="645d4-136">Users must be signed in.</span></span> <span data-ttu-id="645d4-137">Anonyma användare ser inte anpassade rekommendationer.</span><span class="sxs-lookup"><span data-stu-id="645d4-137">Anonymous users won't see personalized recommendations.</span></span>
- <span data-ttu-id="645d4-138">Användarna måste ha minst ett inköp på sitt konto.</span><span class="sxs-lookup"><span data-stu-id="645d4-138">Users must have at least one purchase on their account.</span></span>
- <span data-ttu-id="645d4-139">Användarna måste välja att få anpassade rekommendationer.</span><span class="sxs-lookup"><span data-stu-id="645d4-139">Users must opt in to receive personalized recommendations.</span></span>

<span data-ttu-id="645d4-140">I bilden nedan visas ett exempel på en lista över "val för dig"-lista på en nätbutiks sida.</span><span class="sxs-lookup"><span data-stu-id="645d4-140">The following illustration shows an example of a "Picks for you" list on an online store page.</span></span>

!["Val för dig"-lista online](./media/picksforyou.png)

### <a name="recommended-for-customer-lists-at-the-pos"></a><span data-ttu-id="645d4-142">"Rekommenderad för kunder"-listor i kassan</span><span class="sxs-lookup"><span data-stu-id="645d4-142">"Recommended for customer" lists at the POS</span></span>

<span data-ttu-id="645d4-143">För att förbättra sin klientelingupplevelse kan återförsäljare anpassa befintliga sidor med kundinformation genom att lägga till en snabb "Rekommenderad för kund"-lista.</span><span class="sxs-lookup"><span data-stu-id="645d4-143">To enhance their clienteling experience, retailers can personalize existing customer details pages by adding a contextual "Recommended for customer" list.</span></span>

<span data-ttu-id="645d4-144">I bilden nedan visas ett exempel på en lista över "rekommenderad för kund"-lista i en kassaterminal.</span><span class="sxs-lookup"><span data-stu-id="645d4-144">The following illustration shows an example of a "Recommended for customer" list on a POS terminal.</span></span>

!["Rekommenderad för kunder"-list i kassan](./media/picksonpos.png)

## <a name="apply-personalization-to-existing-recommendation-lists"></a><span data-ttu-id="645d4-146">Använd anpassningar för befintliga rekommendationslistor</span><span class="sxs-lookup"><span data-stu-id="645d4-146">Apply personalization to existing recommendation lists</span></span>

<span data-ttu-id="645d4-147">Återförsäljare kan göra anpassningar av befintliga rekommendationslistor, t.ex. "nytt", "trend", "bästsäljare", "människor gillar också" och "köps ofta ihop".</span><span class="sxs-lookup"><span data-stu-id="645d4-147">Retailers can apply personalization to existing recommendation lists, such as "New," "Trending," "Best selling," "People also like," and "Frequently bought together."</span></span> <span data-ttu-id="645d4-148">När anpassningar tillämpas på befintliga listor, tas de objekt som en inloggad användare tidigare köpt bort från dessa listor.</span><span class="sxs-lookup"><span data-stu-id="645d4-148">When personalization is applied to existing lists, items that a signed-in user previously bought are removed from those lists.</span></span> <span data-ttu-id="645d4-149">För både anonyma användare och användare som väljer att få anpassade rekommendationer visas standardversionerna av de befintliga listorna.</span><span class="sxs-lookup"><span data-stu-id="645d4-149">For both anonymous users and users who opted out of receiving personalized recommendations, default versions of the existing lists are shown.</span></span> <span data-ttu-id="645d4-150">Därför behöver inte detaljister manuellt upprätthålla separata sidupplevelser.</span><span class="sxs-lookup"><span data-stu-id="645d4-150">Therefore, retailers don't have to manually maintain separate page experiences.</span></span>

<span data-ttu-id="645d4-151">En inloggad användare har till exempel redan köpt den svarta klockan och de bruna arbetsstövlar som visas i listan "trend - standard" i följande bild.</span><span class="sxs-lookup"><span data-stu-id="645d4-151">For example, a signed-in user has already bought the black watch and the brown work boots that appear in the "Trending - default" list in the following illustration.</span></span> <span data-ttu-id="645d4-152">Därför kommer användarna att se nya produkter i stället för dessa produkter, som de visas i listan "trend - anpassa".</span><span class="sxs-lookup"><span data-stu-id="645d4-152">Therefore, the user will see new products instead of those products, as shown in the "Trending - personalized" list.</span></span>

![Använda anpassning](./media/applypersonalization.png)

<span data-ttu-id="645d4-154">Om du vill använda anpassningar för en befintlig rekommendations lista i webbplatsskaparen för Handel följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="645d4-154">To apply personalization to an existing recommendation list in the Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="645d4-155">Öppna en befintlig sidan i webbplatsskaparen som innehåller en modul för produktinsamling.</span><span class="sxs-lookup"><span data-stu-id="645d4-155">Open an existing site builder page that contains a product collection module.</span></span>
1. <span data-ttu-id="645d4-156">I vänster navigeringsfönstret, välj produktinsamlingsmodul.</span><span class="sxs-lookup"><span data-stu-id="645d4-156">In the left navigation pane, select the product collection module.</span></span>
1. <span data-ttu-id="645d4-157">I höger navigeringsfönstret, under **Produkter** väljer du listan.</span><span class="sxs-lookup"><span data-stu-id="645d4-157">In the right navigation pane, under **Products**, select the list.</span></span>
1. <span data-ttu-id="645d4-158">I dialogrutan **Välj konfiguration för produktlista**, under **Typ**, välj listtyp.</span><span class="sxs-lookup"><span data-stu-id="645d4-158">In the **Select product list configuration** dialog box, under **Type**, select the list type.</span></span>
1. <span data-ttu-id="645d4-159">Markera kryssrutan **Använd anpassning** och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="645d4-159">Select the **Apply Personalization** check box, and then select **OK**.</span></span>

    ![Använda anpassningar i en trendlista](./media/ApplyPersonalizationToTrending.PNG)

1. <span data-ttu-id="645d4-161">Spara sidan, slutför redigeringen av den och publicera den.</span><span class="sxs-lookup"><span data-stu-id="645d4-161">Save the page, finish editing it, and then publish it.</span></span> <span data-ttu-id="645d4-162">När sidan har publicerats kommer de inloggade användarna att se anpassade trendlistor.</span><span class="sxs-lookup"><span data-stu-id="645d4-162">After the page is published, signed-in users will see personalized trending lists.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="645d4-163">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="645d4-163">Additional resources</span></span>

[<span data-ttu-id="645d4-164">Översikt av produktrekommendationer</span><span class="sxs-lookup"><span data-stu-id="645d4-164">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="645d4-165">Aktivera Azure Data Lake Storage i en Dynamics 365 Commerce-miljö</span><span class="sxs-lookup"><span data-stu-id="645d4-165">Enable Azure Data Lake Storage in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="645d4-166">Aktivera produktrekommendationer</span><span class="sxs-lookup"><span data-stu-id="645d4-166">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="645d4-167">Aktivera rekommendationer för "köp liknande produkter"</span><span class="sxs-lookup"><span data-stu-id="645d4-167">Enable "shop similar looks" recommendations</span></span>](shop-similar-looks.md)

[<span data-ttu-id="645d4-168">Avanmäl anpassade rekommendationer</span><span class="sxs-lookup"><span data-stu-id="645d4-168">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="645d4-169">Lägg till produktrekommendationer i kassan</span><span class="sxs-lookup"><span data-stu-id="645d4-169">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="645d4-170">Lägg till rekommendationer på transaktionsskärmen</span><span class="sxs-lookup"><span data-stu-id="645d4-170">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="645d4-171">Justera rekommendationsresultat från AI-ML</span><span class="sxs-lookup"><span data-stu-id="645d4-171">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="645d4-172">Skapa granskade rekommendationer manuellt</span><span class="sxs-lookup"><span data-stu-id="645d4-172">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="645d4-173">Skapa rekommendationer med demodata</span><span class="sxs-lookup"><span data-stu-id="645d4-173">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)

[<span data-ttu-id="645d4-174">Vanliga frågor om produktrekommendationer</span><span class="sxs-lookup"><span data-stu-id="645d4-174">Product recommendations FAQ</span></span>](faq-recommendations.md)
