---
title: Aktivera produktrekommendationer
description: I det här avsnittet beskrivs hur du gör produktrekommendationer som baseras på artificiell intelligens (AI-ML) tillgängligt för Microsoft Dynamics 365 Commerce-kunder.
author: bebeale
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: ''
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 694e5a451b8e25f3729364dfaed0adc7d242f2fe
ms.sourcegitcommit: fdc5dd9eb784c7d8e75692c8cdba083fe0dd87ce
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/26/2020
ms.locfileid: "3404219"
---
# <a name="enable-product-recommendations"></a><span data-ttu-id="5b8d9-103">Aktivera produktrekommendationer</span><span class="sxs-lookup"><span data-stu-id="5b8d9-103">Enable product recommendations</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="5b8d9-104">I det här avsnittet beskrivs hur du gör produktrekommendationer som baseras på artificiell intelligens (AI-ML) tillgängligt för Microsoft Dynamics 365 Commerce-kunder.</span><span class="sxs-lookup"><span data-stu-id="5b8d9-104">This topic explains how to make product recommendations that are based on artificial intelligence-machine learning (AI-ML) available for Microsoft Dynamics 365 Commerce customers.</span></span> <span data-ttu-id="5b8d9-105">Mer information om produktrekommendationslistor finns i [produktrekommendationer - översikt](product-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="5b8d9-105">For more information about product recommendation lists, see [Product recommendations overview](product-recommendations.md).</span></span>

## <a name="recommendations-pre-check"></a><span data-ttu-id="5b8d9-106">Förkontroll av rekommendationer</span><span class="sxs-lookup"><span data-stu-id="5b8d9-106">Recommendations pre-check</span></span>

<span data-ttu-id="5b8d9-107">Innan du aktiverar produkten bör du notera att produktrekommendationer endast stöds för handelskunder som har migrerat deras lagring till att använda Azure Data Lake Storage.</span><span class="sxs-lookup"><span data-stu-id="5b8d9-107">Before enabling, note that product recommendations are only supported for Commerce customers who have migrated their storage to using Azure Data Lake Storage.</span></span> 

<span data-ttu-id="5b8d9-108">Följande konfigurationer måste aktiveras på baksidan innan rekommendationer aktiveras:</span><span class="sxs-lookup"><span data-stu-id="5b8d9-108">The following configurations must be enabled in the back office before enabling recommendations:</span></span>

1. <span data-ttu-id="5b8d9-109">Kontrollera att Azure Data Lake Storage har köpts och kontrollerats i miljön.</span><span class="sxs-lookup"><span data-stu-id="5b8d9-109">Ensure that Azure Data Lake Storage has been purchased and successfully verified in the environment.</span></span> <span data-ttu-id="5b8d9-110">För mer information, se [Kontrollera att Azure Data Lake Storage har köpts och kontrollerats i miljön](enable-ADLS-environment.md).</span><span class="sxs-lookup"><span data-stu-id="5b8d9-110">For more information, see [Ensure that Azure Data Lake Storage has been purchased and successfully verified in the environment](enable-ADLS-environment.md).</span></span>
2. <span data-ttu-id="5b8d9-111">Kontrollera att uppdatering av enhetslagring är automatiserat.</span><span class="sxs-lookup"><span data-stu-id="5b8d9-111">Ensure that the entity store refresh has been automated.</span></span> <span data-ttu-id="5b8d9-112">Mer information finns i [kontrollera att uppdatering av enhetsarkivet har automatiserats](../fin-ops-core/dev-itpro/data-entities/entity-store-data-lake.md).</span><span class="sxs-lookup"><span data-stu-id="5b8d9-112">For more information, see [Ensure that the Entity store refresh has been automated](../fin-ops-core/dev-itpro/data-entities/entity-store-data-lake.md).</span></span>
3. <span data-ttu-id="5b8d9-113">Bekräfta att Azure AD identitetskonfigurationen innehåller en post för rekommendationer.</span><span class="sxs-lookup"><span data-stu-id="5b8d9-113">Confirm that Azure AD Identity configuration contains an entry for Recommendations.</span></span> <span data-ttu-id="5b8d9-114">Mer information om hur du utför den här åtgärden finns nedan.</span><span class="sxs-lookup"><span data-stu-id="5b8d9-114">More information on how to do this action is below.</span></span>

<span data-ttu-id="5b8d9-115">Kontrollera också att RetailSale-mätningar har aktiverats.</span><span class="sxs-lookup"><span data-stu-id="5b8d9-115">Additionally, ensure that RetailSale measurements have been enabled.</span></span> <span data-ttu-id="5b8d9-116">Mer information om den här inställningsprocessen finns i [arbeta med mått](https://docs.microsoft.com/dynamics365/ai/customer-insights/pm-measures).</span><span class="sxs-lookup"><span data-stu-id="5b8d9-116">To learn more about this set up process, see [Work with measures](https://docs.microsoft.com/dynamics365/ai/customer-insights/pm-measures).</span></span>

## <a name="azure-ad-identity-configuration"></a><span data-ttu-id="5b8d9-117">Azure AD identitetskonfiguration</span><span class="sxs-lookup"><span data-stu-id="5b8d9-117">Azure AD Identity configuration</span></span>

<span data-ttu-id="5b8d9-118">Det här steget krävs för alla kunder som kör infrastruktur som en tjänst (IaaS) konfiguration.</span><span class="sxs-lookup"><span data-stu-id="5b8d9-118">This step is required for all customers running an infra-structure as a service (IaaS) configuration.</span></span> <span data-ttu-id="5b8d9-119">För kunder som kör on Service Fabric (SF) ska det här steget vara automatiskt och vi rekommenderar att du bekräftar att inställningen är konfigurerad som förväntat.</span><span class="sxs-lookup"><span data-stu-id="5b8d9-119">For customers running on service fabric (SF), this step should be automatic and we recommend verifying the setting is configured as expected.</span></span>

### <a name="setup"></a><span data-ttu-id="5b8d9-120">Konfigurera</span><span class="sxs-lookup"><span data-stu-id="5b8d9-120">Setup</span></span>

1. <span data-ttu-id="5b8d9-121">Från backoffice sök efter sidan **Azure Active Directory-program**.</span><span class="sxs-lookup"><span data-stu-id="5b8d9-121">From the back office, search for the **Azure Active Directory applications** page.</span></span>
2. <span data-ttu-id="5b8d9-122">Kontrollera om det finns en post för "RecommendationSystemApplication-1".</span><span class="sxs-lookup"><span data-stu-id="5b8d9-122">Verify if an entry exists for "RecommendationSystemApplication-1".</span></span>

<span data-ttu-id="5b8d9-123">Om posten inte finns lägger du till en ny post med följande information:</span><span class="sxs-lookup"><span data-stu-id="5b8d9-123">If the entry does not exist, add a new entry with the following information:</span></span>

- <span data-ttu-id="5b8d9-124">**Klient-ID** - d37b07e8-dd1c-4514-835d-8b918e6f9727</span><span class="sxs-lookup"><span data-stu-id="5b8d9-124">**Client Id** - d37b07e8-dd1c-4514-835d-8b918e6f9727</span></span>
- <span data-ttu-id="5b8d9-125">**Namn** - RecommendationSystemApplication-1</span><span class="sxs-lookup"><span data-stu-id="5b8d9-125">**Name** - RecommendationSystemApplication-1</span></span>
- <span data-ttu-id="5b8d9-126">**Användar-ID** - RetailServiceAccount</span><span class="sxs-lookup"><span data-stu-id="5b8d9-126">**User Id** - RetailServiceAccount</span></span>

<span data-ttu-id="5b8d9-127">Spara och stäng formuläret</span><span class="sxs-lookup"><span data-stu-id="5b8d9-127">Save and close the page.</span></span> 

## <a name="turn-on-recommendations"></a><span data-ttu-id="5b8d9-128">Aktivera rekommendationer</span><span class="sxs-lookup"><span data-stu-id="5b8d9-128">Turn on recommendations</span></span>

<span data-ttu-id="5b8d9-129">Så här aktiverar du produktrekommendationer.</span><span class="sxs-lookup"><span data-stu-id="5b8d9-129">To turn on product recommendations, follow these steps.</span></span>

1. <span data-ttu-id="5b8d9-130">Gå till **Butik och handel &gt; Produktrekommendationer &gt; Rekommendationsparametrar**.</span><span class="sxs-lookup"><span data-stu-id="5b8d9-130">Go to **Retail and Commerce &gt; Product recommendations &gt; Recommendation parameters**.</span></span>
1. <span data-ttu-id="5b8d9-131">I listan över delade parametrar, välj **Rekommendationslistor**.</span><span class="sxs-lookup"><span data-stu-id="5b8d9-131">In the list of shared parameters, select **Recommendation Lists**.</span></span>
1. <span data-ttu-id="5b8d9-132">Ge alternativet **Aktivera rekommendationer** värdet **Ja**.</span><span class="sxs-lookup"><span data-stu-id="5b8d9-132">Set the **Enable recommendations** option to **Yes**.</span></span>

![Aktivera rekommendationer](./media/enablepersonalization.png)

> [!NOTE]
> <span data-ttu-id="5b8d9-134">I den här proceduren inleds processen med att generera listor över produktrekommendationer.</span><span class="sxs-lookup"><span data-stu-id="5b8d9-134">This procedure starts the process of generating product recommendation lists.</span></span> <span data-ttu-id="5b8d9-135">Det kan ta flera timmar innan listorna är tillgängliga och kan visas i kassan (POS) eller i Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="5b8d9-135">It may take several hours before the lists are available and can be viewed at the point of sale (POS) or in Dynamics 365 Commerce.</span></span>

## <a name="configure-recommendation-list-parameters"></a><span data-ttu-id="5b8d9-136">Konfigurera parametrar för rekommendationslista</span><span class="sxs-lookup"><span data-stu-id="5b8d9-136">Configure recommendation list parameters</span></span>

<span data-ttu-id="5b8d9-137">Som standard innehåller listan AI-ML-baserad produktrekommendation förslagna värden.</span><span class="sxs-lookup"><span data-stu-id="5b8d9-137">By default, the AI-ML-based product recommendation list provides suggested values.</span></span> <span data-ttu-id="5b8d9-138">Du kan ändra de föreslagna standardvärdena så att de passar affärsflödet.</span><span class="sxs-lookup"><span data-stu-id="5b8d9-138">You can change the default suggested values to suit the flow of your business.</span></span> <span data-ttu-id="5b8d9-139">Om du vill veta mer om hur du ändrar standardparametrarna kan du gå till [Hantera AI-ML-baserade produktrekommendationsresultat](modify-product-recommendation-results.md).</span><span class="sxs-lookup"><span data-stu-id="5b8d9-139">To learn more about how to change the default parameters, go to [Manage AI-ML-based product recommendation results](modify-product-recommendation-results.md).</span></span>

## <a name="show-recommendations-on-pos-devices"></a><span data-ttu-id="5b8d9-140">Visa rekommendationer på kassaenheter</span><span class="sxs-lookup"><span data-stu-id="5b8d9-140">Show recommendations on POS devices</span></span>

<span data-ttu-id="5b8d9-141">När du har aktiverat rekommendationer i backoffice för Handel måste rekommendationspanelen läggas till i kassans kontrollskärm via layoutverktyget.</span><span class="sxs-lookup"><span data-stu-id="5b8d9-141">After enabling recommendations in Commerce back office, the recommendations panel must be added to the control POS screen using the layout tool.</span></span> <span data-ttu-id="5b8d9-142">Mer information om den här processen finns i [Lägga till en rekommendationskontroll till transaktionsskärmen på kassaenheter](add-recommendations-control-pos-screen.md).</span><span class="sxs-lookup"><span data-stu-id="5b8d9-142">To learn about this process, see [Add a recommendations control to the transaction screen on POS devices](add-recommendations-control-pos-screen.md).</span></span> 

## <a name="enable-personalized-recommendations"></a><span data-ttu-id="5b8d9-143">Aktivera anpassade rekommendationer</span><span class="sxs-lookup"><span data-stu-id="5b8d9-143">Enable personalized recommendations</span></span>

<span data-ttu-id="5b8d9-144">I Dynamics 365 Commerce kan återförsäljare göra anpassade produktrekommendationer (även kallade anpassningar) tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="5b8d9-144">In Dynamics 365 Commerce, retailers can make personalized product recommendations (also known as personalization) available.</span></span> <span data-ttu-id="5b8d9-145">På detta sätt kan personliga rekommendationer införlivas i kundupplevelsen online och i kassan.</span><span class="sxs-lookup"><span data-stu-id="5b8d9-145">In this way, personalized recommendations can be incorporated into the online customer experience and at the point of sale.</span></span> <span data-ttu-id="5b8d9-146">När anpassningsfunktionen är aktiverad kan systemet associera en användares inköps- och produktinformation för att skapa enskilda produktrekommendationer.</span><span class="sxs-lookup"><span data-stu-id="5b8d9-146">When the personalization functionality is turned on, the system can associate a user's purchase and product information to generate individualized product recommendations.</span></span>

<span data-ttu-id="5b8d9-147">Mer information om anpassade rekommendationer finns i [aktivera anpassade rekommendationer](personalized-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="5b8d9-147">To learn more about personalized recommendations, see [Enable personalized recommendations](personalized-recommendations.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5b8d9-148">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="5b8d9-148">Additional resources</span></span>

[<span data-ttu-id="5b8d9-149">Översikt av produktrekommendationer</span><span class="sxs-lookup"><span data-stu-id="5b8d9-149">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="5b8d9-150">Aktivera Azure Data Lake Storage i en Dynamics 365 Commerce-miljö</span><span class="sxs-lookup"><span data-stu-id="5b8d9-150">Enable Azure Data Lake Storage in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="5b8d9-151">Aktivera anpassade rekommendationer</span><span class="sxs-lookup"><span data-stu-id="5b8d9-151">Enable personalized recommendations</span></span>](personalized-recommendations.md)

[<span data-ttu-id="5b8d9-152">Avanmäl anpassade rekommendationer</span><span class="sxs-lookup"><span data-stu-id="5b8d9-152">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="5b8d9-153">Lägg till produktrekommendationer i kassan</span><span class="sxs-lookup"><span data-stu-id="5b8d9-153">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="5b8d9-154">Lägg till rekommendationer på transaktionsskärmen</span><span class="sxs-lookup"><span data-stu-id="5b8d9-154">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="5b8d9-155">Justera rekommendationsresultat från AI-ML</span><span class="sxs-lookup"><span data-stu-id="5b8d9-155">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="5b8d9-156">Skapa granskade rekommendationer manuellt</span><span class="sxs-lookup"><span data-stu-id="5b8d9-156">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="5b8d9-157">Skapa rekommendationer med demodata</span><span class="sxs-lookup"><span data-stu-id="5b8d9-157">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)

[<span data-ttu-id="5b8d9-158">Vanliga frågor om produktrekommendationer</span><span class="sxs-lookup"><span data-stu-id="5b8d9-158">Product recommendations FAQ</span></span>](faq-recommendations.md)

