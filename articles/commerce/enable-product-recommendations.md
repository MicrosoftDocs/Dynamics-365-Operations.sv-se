---
title: Aktivera produktrekommendationer
description: I det här avsnittet beskrivs hur du gör produktrekommendationer som baseras på artificiell intelligens (AI-ML) tillgängligt för Microsoft Dynamics 365 Commerce-kunder.
author: bebeale
ms.date: 08/18/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 873266405638cd277eb748ad7e966ba8a4976b13
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6019869"
---
# <a name="enable-product-recommendations"></a><span data-ttu-id="6b549-103">Aktivera produktrekommendationer</span><span class="sxs-lookup"><span data-stu-id="6b549-103">Enable product recommendations</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="6b549-104">I det här avsnittet beskrivs hur du gör produktrekommendationer som baseras på artificiell intelligens (AI-ML) tillgängligt för Microsoft Dynamics 365 Commerce-kunder.</span><span class="sxs-lookup"><span data-stu-id="6b549-104">This topic explains how to make product recommendations that are based on artificial intelligence-machine learning (AI-ML) available for Microsoft Dynamics 365 Commerce customers.</span></span> <span data-ttu-id="6b549-105">Mer information om produktrekommendationslistor finns i [produktrekommendationer – översikt](product-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="6b549-105">For more information about product recommendation lists, see [Product recommendations overview](product-recommendations.md).</span></span>

## <a name="recommendations-pre-check"></a><span data-ttu-id="6b549-106">Förkontroll av rekommendationer</span><span class="sxs-lookup"><span data-stu-id="6b549-106">Recommendations pre-check</span></span>

<span data-ttu-id="6b549-107">Innan du aktiverar produkten bör du notera att produktrekommendationer endast stöds för handelskunder som har migrerat deras lagring till att använda Azure Data Lake Storage.</span><span class="sxs-lookup"><span data-stu-id="6b549-107">Before enabling, note that product recommendations are only supported for Commerce customers who have migrated their storage to using Azure Data Lake Storage.</span></span> 

<span data-ttu-id="6b549-108">Följande konfigurationer måste aktiveras på baksidan innan rekommendationer aktiveras:</span><span class="sxs-lookup"><span data-stu-id="6b549-108">The following configurations must be enabled in the back office before enabling recommendations:</span></span>

1. <span data-ttu-id="6b549-109">Kontrollera att Azure Data Lake Storage har köpts och kontrollerats i miljön.</span><span class="sxs-lookup"><span data-stu-id="6b549-109">Ensure that Azure Data Lake Storage has been purchased and successfully verified in the environment.</span></span> <span data-ttu-id="6b549-110">För mer information, se [Kontrollera att Azure Data Lake Storage har köpts och kontrollerats i miljön](enable-ADLS-environment.md).</span><span class="sxs-lookup"><span data-stu-id="6b549-110">For more information, see [Ensure that Azure Data Lake Storage has been purchased and successfully verified in the environment](enable-ADLS-environment.md).</span></span>
2. <span data-ttu-id="6b549-111">Kontrollera att uppdatering av enhetslagring är automatiserat.</span><span class="sxs-lookup"><span data-stu-id="6b549-111">Ensure that the entity store refresh has been automated.</span></span> <span data-ttu-id="6b549-112">Mer information finns i [kontrollera att uppdatering av enhetsarkivet har automatiserats](../fin-ops-core/dev-itpro/data-entities/entity-store-data-lake.md).</span><span class="sxs-lookup"><span data-stu-id="6b549-112">For more information, see [Ensure that the Entity store refresh has been automated](../fin-ops-core/dev-itpro/data-entities/entity-store-data-lake.md).</span></span>
3. <span data-ttu-id="6b549-113">Bekräfta att Azure AD identitetskonfigurationen innehåller en post för rekommendationer.</span><span class="sxs-lookup"><span data-stu-id="6b549-113">Confirm that Azure AD Identity configuration contains an entry for Recommendations.</span></span> <span data-ttu-id="6b549-114">Mer information om hur du utför den här åtgärden finns nedan.</span><span class="sxs-lookup"><span data-stu-id="6b549-114">More information on how to do this action is below.</span></span>

<span data-ttu-id="6b549-115">Kontrollera också att RetailSale-mätningar har aktiverats.</span><span class="sxs-lookup"><span data-stu-id="6b549-115">Additionally, ensure that RetailSale measurements have been enabled.</span></span> <span data-ttu-id="6b549-116">Mer information om den här inställningsprocessen finns i [arbeta med mått](/dynamics365/ai/customer-insights/pm-measures).</span><span class="sxs-lookup"><span data-stu-id="6b549-116">To learn more about this set up process, see [Work with measures](/dynamics365/ai/customer-insights/pm-measures).</span></span>

## <a name="azure-ad-identity-configuration"></a><span data-ttu-id="6b549-117">Azure AD identitetskonfiguration</span><span class="sxs-lookup"><span data-stu-id="6b549-117">Azure AD Identity configuration</span></span>

<span data-ttu-id="6b549-118">Det här steget krävs för alla kunder som kör infrastruktur som en tjänst (IaaS) konfiguration.</span><span class="sxs-lookup"><span data-stu-id="6b549-118">This step is required for all customers running an infra-structure as a service (IaaS) configuration.</span></span> <span data-ttu-id="6b549-119">För kunder som kör on Service Fabric (SF) ska det här steget vara automatiskt och vi rekommenderar att du bekräftar att inställningen är konfigurerad som förväntat.</span><span class="sxs-lookup"><span data-stu-id="6b549-119">For customers running on service fabric (SF), this step should be automatic and we recommend verifying the setting is configured as expected.</span></span>

### <a name="setup"></a><span data-ttu-id="6b549-120">Konfigurera</span><span class="sxs-lookup"><span data-stu-id="6b549-120">Setup</span></span>

1. <span data-ttu-id="6b549-121">Från backoffice sök efter sidan **Azure Active Directory-program**.</span><span class="sxs-lookup"><span data-stu-id="6b549-121">From the back office, search for the **Azure Active Directory applications** page.</span></span>
2. <span data-ttu-id="6b549-122">Kontrollera om det finns en post för "RecommendationSystemApplication-1".</span><span class="sxs-lookup"><span data-stu-id="6b549-122">Verify if an entry exists for "RecommendationSystemApplication-1".</span></span>

<span data-ttu-id="6b549-123">Om posten inte finns lägger du till en ny post med följande information:</span><span class="sxs-lookup"><span data-stu-id="6b549-123">If the entry does not exist, add a new entry with the following information:</span></span>

- <span data-ttu-id="6b549-124">**Klient-ID** – d37b07e8-dd1c-4514-835d-8b918e6f9727</span><span class="sxs-lookup"><span data-stu-id="6b549-124">**Client Id** - d37b07e8-dd1c-4514-835d-8b918e6f9727</span></span>
- <span data-ttu-id="6b549-125">**Namn** – RecommendationSystemApplication-1</span><span class="sxs-lookup"><span data-stu-id="6b549-125">**Name** - RecommendationSystemApplication-1</span></span>
- <span data-ttu-id="6b549-126">**Användar-ID** – RetailServiceAccount</span><span class="sxs-lookup"><span data-stu-id="6b549-126">**User Id** - RetailServiceAccount</span></span>

<span data-ttu-id="6b549-127">Spara och stäng formuläret</span><span class="sxs-lookup"><span data-stu-id="6b549-127">Save and close the page.</span></span> 

## <a name="turn-on-recommendations"></a><span data-ttu-id="6b549-128">Aktivera rekommendationer</span><span class="sxs-lookup"><span data-stu-id="6b549-128">Turn on recommendations</span></span>

<span data-ttu-id="6b549-129">Så här aktiverar du produktrekommendationer.</span><span class="sxs-lookup"><span data-stu-id="6b549-129">To turn on product recommendations, follow these steps.</span></span>

1. <span data-ttu-id="6b549-130">Sök efter **funktionshantering** i Commerce Headquarters.</span><span class="sxs-lookup"><span data-stu-id="6b549-130">In Commerce headquarters, search for **Feature Management**.</span></span>
1. <span data-ttu-id="6b549-131">Välj **alla** om du vill visa en lista över tillgängliga funktioner.</span><span class="sxs-lookup"><span data-stu-id="6b549-131">Select **All** to see a list of available features.</span></span> 
1. <span data-ttu-id="6b549-132">Ange **rekommendationer** i sökrutan.</span><span class="sxs-lookup"><span data-stu-id="6b549-132">In the search box, enter **Recommendations**.</span></span>
1. <span data-ttu-id="6b549-133">Välj funktionen **produktrekommendationer**.</span><span class="sxs-lookup"><span data-stu-id="6b549-133">Select the **Product recommendations** feature.</span></span>
1. <span data-ttu-id="6b549-134">I egenskapsfönstret **produktrekommendationer** välj **Aktivera nu**.</span><span class="sxs-lookup"><span data-stu-id="6b549-134">In the **Product recommendations** properties pane, select **Enable now**.</span></span>

![Aktivera rekommendationer](./media/FeatureManagement_Recommendations.PNG)

> [!NOTE]
> <span data-ttu-id="6b549-136">I den här proceduren inleds processen med att generera listor över produktrekommendationer.</span><span class="sxs-lookup"><span data-stu-id="6b549-136">This procedure starts the process of generating product recommendation lists.</span></span> <span data-ttu-id="6b549-137">Det kan ta flera timmar innan listorna är tillgängliga och kan visas i POS eller i Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="6b549-137">It may take several hours before the lists are available and can be viewed at the point of sale (POS) or in Dynamics 365 Commerce.</span></span>

## <a name="configure-recommendation-list-parameters"></a><span data-ttu-id="6b549-138">Konfigurera parametrar för rekommendationslista</span><span class="sxs-lookup"><span data-stu-id="6b549-138">Configure recommendation list parameters</span></span>

<span data-ttu-id="6b549-139">Som standard innehåller listan AI-ML-baserad produktrekommendation förslagna värden.</span><span class="sxs-lookup"><span data-stu-id="6b549-139">By default, the AI-ML-based product recommendation list provides suggested values.</span></span> <span data-ttu-id="6b549-140">Du kan ändra de föreslagna standardvärdena så att de passar affärsflödet.</span><span class="sxs-lookup"><span data-stu-id="6b549-140">You can change the default suggested values to suit the flow of your business.</span></span> <span data-ttu-id="6b549-141">Om du vill veta mer om hur du ändrar standardparametrarna kan du gå till [Hantera AI-ML-baserade produktrekommendationsresultat](modify-product-recommendation-results.md).</span><span class="sxs-lookup"><span data-stu-id="6b549-141">To learn more about how to change the default parameters, go to [Manage AI-ML-based product recommendation results](modify-product-recommendation-results.md).</span></span>

## <a name="show-recommendations-on-pos-devices"></a><span data-ttu-id="6b549-142">Visa rekommendationer på kassaenheter</span><span class="sxs-lookup"><span data-stu-id="6b549-142">Show recommendations on POS devices</span></span>

<span data-ttu-id="6b549-143">När du har aktiverat rekommendationer i backoffice för Commerce måste rekommendationspanelen läggas till i kassans kontrollskärm via layoutverktyget.</span><span class="sxs-lookup"><span data-stu-id="6b549-143">After enabling recommendations in Commerce back office, the recommendations panel must be added to the control POS screen using the layout tool.</span></span> <span data-ttu-id="6b549-144">Mer information om den här processen finns i [Lägga till en rekommendationskontroll till transaktionsskärmen på kassaenheter](add-recommendations-control-pos-screen.md).</span><span class="sxs-lookup"><span data-stu-id="6b549-144">To learn about this process, see [Add a recommendations control to the transaction screen on POS devices](add-recommendations-control-pos-screen.md).</span></span> 

## <a name="enable-personalized-recommendations"></a><span data-ttu-id="6b549-145">Aktivera anpassade rekommendationer</span><span class="sxs-lookup"><span data-stu-id="6b549-145">Enable personalized recommendations</span></span>

<span data-ttu-id="6b549-146">I Dynamics 365 Commerce kan återförsäljare göra anpassade produktrekommendationer (även kallade anpassningar) tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="6b549-146">In Dynamics 365 Commerce, retailers can make personalized product recommendations (also known as personalization) available.</span></span> <span data-ttu-id="6b549-147">På detta sätt kan personliga rekommendationer införlivas i kundupplevelsen online och i POS.</span><span class="sxs-lookup"><span data-stu-id="6b549-147">In this way, personalized recommendations can be incorporated into the online customer experience and at the point of sale.</span></span> <span data-ttu-id="6b549-148">När anpassningsfunktionen är aktiverad kan systemet associera en användares inköps- och produktinformation för att skapa enskilda produktrekommendationer.</span><span class="sxs-lookup"><span data-stu-id="6b549-148">When the personalization functionality is turned on, the system can associate a user's purchase and product information to generate individualized product recommendations.</span></span>

<span data-ttu-id="6b549-149">Mer information om anpassade rekommendationer finns i [aktivera anpassade rekommendationer](personalized-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="6b549-149">To learn more about personalized recommendations, see [Enable personalized recommendations](personalized-recommendations.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6b549-150">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="6b549-150">Additional resources</span></span>

[<span data-ttu-id="6b549-151">Översikt av produktrekommendationer</span><span class="sxs-lookup"><span data-stu-id="6b549-151">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="6b549-152">Aktivera Azure Data Lake Storage i en Dynamics 365 Commerce-miljö</span><span class="sxs-lookup"><span data-stu-id="6b549-152">Enable Azure Data Lake Storage in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="6b549-153">Aktivera anpassade rekommendationer</span><span class="sxs-lookup"><span data-stu-id="6b549-153">Enable personalized recommendations</span></span>](personalized-recommendations.md)

[<span data-ttu-id="6b549-154">Aktivera rekommendationer för "köp liknande produkter"</span><span class="sxs-lookup"><span data-stu-id="6b549-154">Enable "shop similar looks" recommendations</span></span>](shop-similar-looks.md)

[<span data-ttu-id="6b549-155">Avanmäl anpassade rekommendationer</span><span class="sxs-lookup"><span data-stu-id="6b549-155">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="6b549-156">Lägg till produktrekommendationer i POS</span><span class="sxs-lookup"><span data-stu-id="6b549-156">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="6b549-157">Lägg till rekommendationer på transaktionsskärmen</span><span class="sxs-lookup"><span data-stu-id="6b549-157">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="6b549-158">Justera rekommendationsresultat från AI-ML</span><span class="sxs-lookup"><span data-stu-id="6b549-158">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="6b549-159">Skapa granskade rekommendationer manuellt</span><span class="sxs-lookup"><span data-stu-id="6b549-159">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="6b549-160">Skapa rekommendationer med demodata</span><span class="sxs-lookup"><span data-stu-id="6b549-160">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)

[<span data-ttu-id="6b549-161">Vanliga frågor om produktrekommendationer</span><span class="sxs-lookup"><span data-stu-id="6b549-161">Product recommendations FAQ</span></span>](faq-recommendations.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]