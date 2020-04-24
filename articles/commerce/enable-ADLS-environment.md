---
title: Aktivera ADLS i en Dynamics 365 Commerce-miljö
description: I det här avsnittet beskrivs hur du aktiverar och testar Azure Data Lake Storage (ADLS) för en Dynamics 365 Commerce-miljö, vilket är en förutsättning för att du ska kunna aktivera produktrekommendationer.
author: bebeale
manager: AnnBe
ms.date: 04/13/2020
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
ms.openlocfilehash: ba428765babb9ca7566da7a457368959b1c29083
ms.sourcegitcommit: dbff1c6bb371a443a0cd2a310f5a48d5c21b08ca
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2020
ms.locfileid: "3259758"
---
# <a name="enable-adls-in-a-dynamics-365-commerce-environment"></a><span data-ttu-id="8897a-103">Aktivera ADLS i en Dynamics 365 Commerce-miljö</span><span class="sxs-lookup"><span data-stu-id="8897a-103">Enable ADLS in a Dynamics 365 Commerce environment</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="8897a-104">I det här avsnittet beskrivs hur du aktiverar och testar Azure Data Lake Storage (ADLS) för en Dynamics 365 Commerce-miljö, vilket är en förutsättning för att du ska kunna aktivera produktrekommendationer.</span><span class="sxs-lookup"><span data-stu-id="8897a-104">This topic explains how to enable and test Azure Data Lake Storage (ADLS) for a Dynamics 365 Commerce environment, which is a prerequisite for enabling product recommendations.</span></span>

## <a name="overview"></a><span data-ttu-id="8897a-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="8897a-105">Overview</span></span>

<span data-ttu-id="8897a-106">I Dynamics 365 Commerce-lösningen spåras all produktinformation och all transaktionsinformation i miljöns enhetsarkiv.</span><span class="sxs-lookup"><span data-stu-id="8897a-106">In the Dynamics 365 Commerce solution, all product and transaction information is tracked in the environment's Entity store.</span></span> <span data-ttu-id="8897a-107">Om du vill göra dessa data tillgängliga för andra Dynamics 365-tjänster, t.ex. dataanalyser, affärsstrategier och anpassade rekommendationer, måste du ansluta miljön till en kundägd Azure Data Lake Storage Gen 2 (ADLS)-lösning.</span><span class="sxs-lookup"><span data-stu-id="8897a-107">To make this data accessible to other Dynamics 365 services, such as data analytics, business intelligence, and personalized recommendations, it is necessary to connect the environment to a customer-owned Azure Data Lake Storage Gen 2 (ADLS) solution.</span></span>

<span data-ttu-id="8897a-108">Eftersom ADLS konfigureras i en miljö, speglas alla nödvändiga data från enhetsarkivet samtidigt som de skyddas och kontrolleras av kunden.</span><span class="sxs-lookup"><span data-stu-id="8897a-108">As ADLS is configured in an environment, all necessary data is mirrored from the Entity store while still being protected and under customer's control.</span></span>

<span data-ttu-id="8897a-109">Om produktrekommendationer eller anpassade rekommendationer också har aktiverats i miljön ger produktrekommendationerna stack åtkomst till den dedikerade mappen i ADLS för att hämta kundens data och beräkna rekommendationer baserat på den.</span><span class="sxs-lookup"><span data-stu-id="8897a-109">If product recommendations or personalized recommendations are also enabled in the environment, then the product recommendations stack will be granted access to the dedicated folder in ADLS to retrieve the customer’s data and compute recommendations based on it.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8897a-110">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="8897a-110">Prerequisites</span></span>

<span data-ttu-id="8897a-111">Kunder måste ha ADLS konfigurerat i en Azure-prenumeration som de äger.</span><span class="sxs-lookup"><span data-stu-id="8897a-111">Customers need to have ADLS configured in an Azure subscription that they own.</span></span> <span data-ttu-id="8897a-112">Det här avsnittet behandlar inte köp av en Azure-prenumeration eller inställningen av ett ADLS-aktiverat lagringskonto.</span><span class="sxs-lookup"><span data-stu-id="8897a-112">This topic does not cover the purchase of an Azure subscription or the setup of an ADLS-enabled storage account.</span></span>

<span data-ttu-id="8897a-113">Mer information om ADLS finns i [officiell ADLS-dokumentation](https://azure.microsoft.com/pricing/details/storage/data-lake).</span><span class="sxs-lookup"><span data-stu-id="8897a-113">For more information about ADLS, see [ADLS official documentation](https://azure.microsoft.com/pricing/details/storage/data-lake).</span></span>
  
## <a name="configuration-steps"></a><span data-ttu-id="8897a-114">Konfigurationssteg</span><span class="sxs-lookup"><span data-stu-id="8897a-114">Configuration steps</span></span>

<span data-ttu-id="8897a-115">I det här avsnittet beskrivs de konfigurationssteg som krävs för att aktivera ADLS i en miljö när det gäller produktrekommendationer.</span><span class="sxs-lookup"><span data-stu-id="8897a-115">This section covers the configuration steps necessary for enabling ADLS in an environment as it relates to product recommendations.</span></span>
<span data-ttu-id="8897a-116">En mer ingående översikt över de steg som krävs för att aktivera ADLS finns i [Gör entitetsbutik tillgänglig som Data Lake](../fin-ops-core/dev-itpro/data-entities/entity-store-data-lake.md).</span><span class="sxs-lookup"><span data-stu-id="8897a-116">For a more in-depth overview of the steps required to enable ADLS, see [Make entity store available as a Data Lake](../fin-ops-core/dev-itpro/data-entities/entity-store-data-lake.md).</span></span>

### <a name="enable-adls-in-the-environment"></a><span data-ttu-id="8897a-117">Aktivera ADLS i miljö</span><span class="sxs-lookup"><span data-stu-id="8897a-117">Enable ADLS in the environment</span></span>

1. <span data-ttu-id="8897a-118">Logga in på miljöns backoffice-Portal.</span><span class="sxs-lookup"><span data-stu-id="8897a-118">Log in to the environment's back office portal.</span></span>
1. <span data-ttu-id="8897a-119">Sök efter **Systemparametrar** och navigera till fliken **Dataanslutningar**.</span><span class="sxs-lookup"><span data-stu-id="8897a-119">Search for **System Parameters** and navigate to the **Data connections** tab.</span></span> 
1. <span data-ttu-id="8897a-120">Ange **Aktivera Data Lake-integrering** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="8897a-120">Set **Enable Data Lake integration** to **Yes**.</span></span>
1. <span data-ttu-id="8897a-121">Ange **Indroppning uppdatering av Data Lake** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="8897a-121">Set **Trickle update Data Lake** to **Yes**.</span></span>
1. <span data-ttu-id="8897a-122">Ange sedan följande obligatorisk information:</span><span class="sxs-lookup"><span data-stu-id="8897a-122">Next, enter the following required information:</span></span>
    1. <span data-ttu-id="8897a-123">**Program-ID** // **Programhemlighet** // **DNS-namn** - Behövs för att ansluta till KeyVault där ADLS-hemligheten lagras.</span><span class="sxs-lookup"><span data-stu-id="8897a-123">**Application ID** // **Application Secret** // **DNS Name** - Needed to connect to KeyVault where the ADLS secret is stored.</span></span>
    1. <span data-ttu-id="8897a-124">**Hemligtnamn** - Det hemliga namnet lagrat i KeyVault och används för att autentisera med ADLS.</span><span class="sxs-lookup"><span data-stu-id="8897a-124">**Secret name** - The secret name stored in KeyVault and used to authenticate with ADLS.</span></span>
1. <span data-ttu-id="8897a-125">Spara ändringarna i det övre vänstra hörnet på sidan.</span><span class="sxs-lookup"><span data-stu-id="8897a-125">Save your changes in the top left corner of the page.</span></span>

<span data-ttu-id="8897a-126">I bilden nedan visas ett exempel på ADLS-konfiguration.</span><span class="sxs-lookup"><span data-stu-id="8897a-126">The following image shows an example ADLS configuration.</span></span>

![Exempel på ADLS-konfiguration](./media/exampleADLSConfig1.png)

### <a name="test-the-adls-connection"></a><span data-ttu-id="8897a-128">Testa ADLS-anslutningen</span><span class="sxs-lookup"><span data-stu-id="8897a-128">Test the ADLS connection</span></span>

1. <span data-ttu-id="8897a-129">Testa anslutningen till KeyVault med hjälp länk **Testa Azure Key Vault**.</span><span class="sxs-lookup"><span data-stu-id="8897a-129">Test the connection to KeyVault using the **Test Azure Key Vault** link.</span></span>
1. <span data-ttu-id="8897a-130">Testa anslutningen till ett ADLS med hjälp länk **Testa Azure Storage**.</span><span class="sxs-lookup"><span data-stu-id="8897a-130">Test the connection to ADLS using the **Test Azure Storage** link.</span></span>

> [!NOTE]
> <span data-ttu-id="8897a-131">Om testerna misslyckas kontrollerar du att all KeyVault-information som lagts till ovan är korrekt och försöker igen.</span><span class="sxs-lookup"><span data-stu-id="8897a-131">If the tests fail, double-check that all of the KeyVault information added above is correct, then try again.</span></span>

<span data-ttu-id="8897a-132">När anslutningstesten har lyckats måste du aktivera automatisk uppdatering för enhetsarkivet.</span><span class="sxs-lookup"><span data-stu-id="8897a-132">Once the connection tests are successful, you must enable automatic refresh for Entity store.</span></span>

<span data-ttu-id="8897a-133">Aktivera automatisk uppdatering för enhetsarkivet genom att följa stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="8897a-133">To enable automatic refresh for Entity store, follow these steps.</span></span>

1. <span data-ttu-id="8897a-134">Sök efter **enhetsarkiv**.</span><span class="sxs-lookup"><span data-stu-id="8897a-134">Search for **Entity Store**.</span></span>
1. <span data-ttu-id="8897a-135">Navigera till listan till vänster till enhet **RetailSales** och välj **redigera**.</span><span class="sxs-lookup"><span data-stu-id="8897a-135">In the list on the left, navigate to the **RetailSales** entry, and select **Edit**.</span></span>
1. <span data-ttu-id="8897a-136">Se till **Automatisk uppdatering är aktiverat** är inställd på **Ja**, välj **Uppdatera** och välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="8897a-136">Ensure that **Automatic Refresh Enabled** is set to **Yes**, select **Refresh**, and then select **Save**.</span></span>

<span data-ttu-id="8897a-137">I bilden nedan visas ett exempel på ett enhetslagring med automatisk uppdatering aktiverat.</span><span class="sxs-lookup"><span data-stu-id="8897a-137">The following image shows an example of Entity store with automatic refresh enabled.</span></span>

![Exempel på enhetslagring med automatisk uppdatering aktiverad](./media/exampleADLSConfig2.png)

<span data-ttu-id="8897a-139">ADLS har nu konfigurerats för miljön.</span><span class="sxs-lookup"><span data-stu-id="8897a-139">ADLS is now configured for the environment.</span></span> 

<span data-ttu-id="8897a-140">Om det inte redan är klart följer du stegen för [aktivera produktrekommendationer och anpassning](enable-product-recommendations.md) för miljön.</span><span class="sxs-lookup"><span data-stu-id="8897a-140">If not completed already, follow the steps for [enabling product recommendations and personalization](enable-product-recommendations.md) for the environment.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8897a-141">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="8897a-141">Additional resources</span></span>

[<span data-ttu-id="8897a-142">Gör enhetslagring tillgängligt som en Data Lake</span><span class="sxs-lookup"><span data-stu-id="8897a-142">Make entity store available as a data lake</span></span>](../fin-ops-core/dev-itpro/data-entities/entity-store-data-lake.md)

[<span data-ttu-id="8897a-143">Översikt av produktrekommendationer</span><span class="sxs-lookup"><span data-stu-id="8897a-143">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="8897a-144">Aktivera produktrekommendationer</span><span class="sxs-lookup"><span data-stu-id="8897a-144">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="8897a-145">Aktivera anpassade rekommendationer</span><span class="sxs-lookup"><span data-stu-id="8897a-145">Enable personalized recommendations</span></span>](personalized-recommendations.md)

[<span data-ttu-id="8897a-146">Avanmäl anpassade rekommendationer</span><span class="sxs-lookup"><span data-stu-id="8897a-146">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="8897a-147">Lägg till produktrekommendationer i kassan</span><span class="sxs-lookup"><span data-stu-id="8897a-147">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="8897a-148">Lägg till rekommendationer på transaktionsskärmen</span><span class="sxs-lookup"><span data-stu-id="8897a-148">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="8897a-149">Justera rekommendationsresultat från AI-ML</span><span class="sxs-lookup"><span data-stu-id="8897a-149">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="8897a-150">Skapa granskade rekommendationer manuellt</span><span class="sxs-lookup"><span data-stu-id="8897a-150">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="8897a-151">Skapa rekommendationer med demodata</span><span class="sxs-lookup"><span data-stu-id="8897a-151">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)

[<span data-ttu-id="8897a-152">Vanliga frågor om produktrekommendationer</span><span class="sxs-lookup"><span data-stu-id="8897a-152">Product recommendations FAQ</span></span>](faq-recommendations.md)
