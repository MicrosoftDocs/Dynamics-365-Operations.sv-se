---
title: Aktivera Azure Data Lake Storage i en Dynamics 365 Commerce-miljö
description: I det här avsnittet beskrivs hur du aktiverar och testar Azure Data Lake Storage för en Dynamics 365 Commerce-miljö, vilket är en förutsättning för att du ska kunna aktivera produktrekommendationer.
author: bebeale
ms.date: 04/13/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 61f96dae0643e3383afd91864e4c145f3b5c04c8
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5792617"
---
# <a name="enable-azure-data-lake-storage-in-a-dynamics-365-commerce-environment"></a><span data-ttu-id="ba5b1-103">Aktivera Azure Data Lake Storage i en Dynamics 365 Commerce-miljö</span><span class="sxs-lookup"><span data-stu-id="ba5b1-103">Enable Azure Data Lake Storage in a Dynamics 365 Commerce environment</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="ba5b1-104">I det här avsnittet beskrivs hur du aktiverar och testar Azure Data Lake Storage för en Dynamics 365 Commerce-miljö, vilket är en förutsättning för att du ska kunna aktivera produktrekommendationer.</span><span class="sxs-lookup"><span data-stu-id="ba5b1-104">This topic explains how to enable and test Azure Data Lake Storage for a Dynamics 365 Commerce environment, which is a prerequisite for enabling product recommendations.</span></span>

<span data-ttu-id="ba5b1-105">I Dynamics 365 Commerce-lösningen spåras all produktinformation och all transaktionsinformation i miljöns enhetsarkiv.</span><span class="sxs-lookup"><span data-stu-id="ba5b1-105">In the Dynamics 365 Commerce solution, all product and transaction information is tracked in the environment's Entity store.</span></span> <span data-ttu-id="ba5b1-106">Om du vill göra dessa data tillgängliga för andra Dynamics 365-tjänster, t.ex. dataanalyser, affärsstrategier och anpassade rekommendationer, måste du ansluta miljön till en kundägd Azure Data Lake Storage Gen 2-lösning.</span><span class="sxs-lookup"><span data-stu-id="ba5b1-106">To make this data accessible to other Dynamics 365 services, such as data analytics, business intelligence, and personalized recommendations, it is necessary to connect the environment to a customer-owned Azure Data Lake Storage Gen 2 solution.</span></span>

<span data-ttu-id="ba5b1-107">Eftersom Azure Data Lake Storage konfigureras i en miljö, speglas alla nödvändiga data från enhetsarkivet samtidigt som de skyddas och kontrolleras av kunden.</span><span class="sxs-lookup"><span data-stu-id="ba5b1-107">As Azure Data Lake Storage is configured in an environment, all necessary data is mirrored from the Entity store while still being protected and under customer's control.</span></span>

<span data-ttu-id="ba5b1-108">Om produktrekommendationer eller anpassade rekommendationer också har aktiverats i miljön ger produktrekommendationerna stack åtkomst till den dedikerade mappen i Azure Data Lake Storage för att hämta kundens data och beräkna rekommendationer baserat på den.</span><span class="sxs-lookup"><span data-stu-id="ba5b1-108">If product recommendations or personalized recommendations are also enabled in the environment, then the product recommendations stack will be granted access to the dedicated folder in Azure Data Lake Storage to retrieve the customer’s data and compute recommendations based on it.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ba5b1-109">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="ba5b1-109">Prerequisites</span></span>

<span data-ttu-id="ba5b1-110">Kunder måste ha Azure Data Lake Storage konfigurerat i en Azure-prenumeration som de äger.</span><span class="sxs-lookup"><span data-stu-id="ba5b1-110">Customers need to have Azure Data Lake Storage configured in an Azure subscription that they own.</span></span> <span data-ttu-id="ba5b1-111">Det här avsnittet behandlar inte köp av en Azure-prenumeration eller inställningen av ett Azure Data Lake Storage-aktiverat lagringskonto.</span><span class="sxs-lookup"><span data-stu-id="ba5b1-111">This topic does not cover the purchase of an Azure subscription or the setup of an Azure Data Lake Storage-enabled storage account.</span></span>

<span data-ttu-id="ba5b1-112">Mer information om Azure Data Lake Storage finns i [Azure Data Lake Storage officiell Gen2-dokumentation](https://azure.microsoft.com/pricing/details/storage/data-lake).</span><span class="sxs-lookup"><span data-stu-id="ba5b1-112">For more information about Azure Data Lake Storage, see [Azure Data Lake Storage Gen2 official documentation](https://azure.microsoft.com/pricing/details/storage/data-lake).</span></span>
  
## <a name="configuration-steps"></a><span data-ttu-id="ba5b1-113">Konfigurationssteg</span><span class="sxs-lookup"><span data-stu-id="ba5b1-113">Configuration steps</span></span>

<span data-ttu-id="ba5b1-114">I det här avsnittet beskrivs de konfigurationssteg som krävs för att aktivera Azure Data Lake Storage i en miljö när det gäller produktrekommendationer.</span><span class="sxs-lookup"><span data-stu-id="ba5b1-114">This section covers the configuration steps necessary for enabling Azure Data Lake Storage in an environment as it relates to product recommendations.</span></span>
<span data-ttu-id="ba5b1-115">En mer ingående översikt över de steg som krävs för att aktivera Azure Data Lake Storage finns i [Gör entitetsbutik tillgänglig som Data Lake](../fin-ops-core/dev-itpro/data-entities/entity-store-data-lake.md).</span><span class="sxs-lookup"><span data-stu-id="ba5b1-115">For a more in-depth overview of the steps required to enable Azure Data Lake Storage, see [Make entity store available as a Data Lake](../fin-ops-core/dev-itpro/data-entities/entity-store-data-lake.md).</span></span>

### <a name="enable-azure-data-lake-storage-in-the-environment"></a><span data-ttu-id="ba5b1-116">Aktivera Azure Data Lake Storage i miljö</span><span class="sxs-lookup"><span data-stu-id="ba5b1-116">Enable Azure Data Lake Storage in the environment</span></span>

1. <span data-ttu-id="ba5b1-117">Logga in på miljöns backoffice-Portal.</span><span class="sxs-lookup"><span data-stu-id="ba5b1-117">Log in to the environment's back office portal.</span></span>
1. <span data-ttu-id="ba5b1-118">Sök efter **Systemparametrar** och navigera till fliken **Dataanslutningar**.</span><span class="sxs-lookup"><span data-stu-id="ba5b1-118">Search for **System Parameters** and navigate to the **Data connections** tab.</span></span> 
1. <span data-ttu-id="ba5b1-119">Ange **Aktivera Data Lake-integrering** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="ba5b1-119">Set **Enable Data Lake integration** to **Yes**.</span></span>
1. <span data-ttu-id="ba5b1-120">Ange **Indroppning uppdatering av Data Lake** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="ba5b1-120">Set **Trickle update Data Lake** to **Yes**.</span></span>
1. <span data-ttu-id="ba5b1-121">Ange sedan följande obligatorisk information:</span><span class="sxs-lookup"><span data-stu-id="ba5b1-121">Next, enter the following required information:</span></span>
    1. <span data-ttu-id="ba5b1-122">**Program-ID** // **Programhemlighet** // **DNS-namn** – Behövs för att ansluta till KeyVault där Azure Data Lake Storage-hemligheten lagras.</span><span class="sxs-lookup"><span data-stu-id="ba5b1-122">**Application ID** // **Application Secret** // **DNS Name** - Needed to connect to KeyVault where the Azure Data Lake Storage secret is stored.</span></span>
    1. <span data-ttu-id="ba5b1-123">**Hemligt namn** – Det hemliga namnet lagrat i KeyVault och används för att autentisera med Azure Data Lake Storage.</span><span class="sxs-lookup"><span data-stu-id="ba5b1-123">**Secret name** - The secret name stored in KeyVault and used to authenticate with Azure Data Lake Storage.</span></span>
1. <span data-ttu-id="ba5b1-124">Spara ändringarna i det övre vänstra hörnet på sidan.</span><span class="sxs-lookup"><span data-stu-id="ba5b1-124">Save your changes in the top left corner of the page.</span></span>

<span data-ttu-id="ba5b1-125">I bilden nedan visas ett exempel på Azure Data Lake Storage-konfiguration.</span><span class="sxs-lookup"><span data-stu-id="ba5b1-125">The following image shows an example Azure Data Lake Storage configuration.</span></span>

![Exempel på Azure Data Lake Storage-konfiguration](./media/exampleADLSConfig1.png)

### <a name="test-the-azure-data-lake-storage-connection"></a><span data-ttu-id="ba5b1-127">Testa Azure Data Lake Storage-anslutningen</span><span class="sxs-lookup"><span data-stu-id="ba5b1-127">Test the Azure Data Lake Storage connection</span></span>

1. <span data-ttu-id="ba5b1-128">Testa anslutningen till KeyVault med hjälp länk **Testa Azure Key Vault**.</span><span class="sxs-lookup"><span data-stu-id="ba5b1-128">Test the connection to KeyVault using the **Test Azure Key Vault** link.</span></span>
1. <span data-ttu-id="ba5b1-129">Testa anslutningen till ett Azure Data Lake Storage med hjälp länk **Testa Azure Storage**.</span><span class="sxs-lookup"><span data-stu-id="ba5b1-129">Test the connection to Azure Data Lake Storage using the **Test Azure Storage** link.</span></span>

> [!NOTE]
> <span data-ttu-id="ba5b1-130">Om testerna misslyckas kontrollerar du att all KeyVault-information som lagts till ovan är korrekt och försöker igen.</span><span class="sxs-lookup"><span data-stu-id="ba5b1-130">If the tests fail, double-check that all of the KeyVault information added above is correct, then try again.</span></span>

<span data-ttu-id="ba5b1-131">När anslutningstesten har lyckats måste du aktivera automatisk uppdatering för enhetsarkivet.</span><span class="sxs-lookup"><span data-stu-id="ba5b1-131">Once the connection tests are successful, you must enable automatic refresh for Entity store.</span></span>

<span data-ttu-id="ba5b1-132">Aktivera automatisk uppdatering för enhetsarkivet genom att följa stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="ba5b1-132">To enable automatic refresh for Entity store, follow these steps.</span></span>

1. <span data-ttu-id="ba5b1-133">Sök efter **enhetsarkiv**.</span><span class="sxs-lookup"><span data-stu-id="ba5b1-133">Search for **Entity Store**.</span></span>
1. <span data-ttu-id="ba5b1-134">Navigera till listan till vänster till enhet **RetailSales** och välj **redigera**.</span><span class="sxs-lookup"><span data-stu-id="ba5b1-134">In the list on the left, navigate to the **RetailSales** entry, and select **Edit**.</span></span>
1. <span data-ttu-id="ba5b1-135">Se till **Automatisk uppdatering är aktiverat** är inställd på **Ja**, välj **Uppdatera** och välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="ba5b1-135">Ensure that **Automatic Refresh Enabled** is set to **Yes**, select **Refresh**, and then select **Save**.</span></span>

<span data-ttu-id="ba5b1-136">I bilden nedan visas ett exempel på ett enhetslagring med automatisk uppdatering aktiverat.</span><span class="sxs-lookup"><span data-stu-id="ba5b1-136">The following image shows an example of Entity store with automatic refresh enabled.</span></span>

![Exempel på enhetslagring med automatisk uppdatering aktiverad](./media/exampleADLSConfig2.png)

<span data-ttu-id="ba5b1-138">Azure Data Lake Storage har nu konfigurerats för miljön.</span><span class="sxs-lookup"><span data-stu-id="ba5b1-138">Azure Data Lake Storage is now configured for the environment.</span></span> 

<span data-ttu-id="ba5b1-139">Om det inte redan är klart följer du stegen för [aktivera produktrekommendationer och anpassning](enable-product-recommendations.md) för miljön.</span><span class="sxs-lookup"><span data-stu-id="ba5b1-139">If not completed already, follow the steps for [enabling product recommendations and personalization](enable-product-recommendations.md) for the environment.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ba5b1-140">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="ba5b1-140">Additional resources</span></span>

[<span data-ttu-id="ba5b1-141">Gör enhetslagring tillgängligt som en Data Lake</span><span class="sxs-lookup"><span data-stu-id="ba5b1-141">Make entity store available as a data lake</span></span>](../fin-ops-core/dev-itpro/data-entities/entity-store-data-lake.md)

[<span data-ttu-id="ba5b1-142">Översikt av produktrekommendationer</span><span class="sxs-lookup"><span data-stu-id="ba5b1-142">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="ba5b1-143">Aktivera produktrekommendationer</span><span class="sxs-lookup"><span data-stu-id="ba5b1-143">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="ba5b1-144">Aktivera anpassade rekommendationer</span><span class="sxs-lookup"><span data-stu-id="ba5b1-144">Enable personalized recommendations</span></span>](personalized-recommendations.md)

[<span data-ttu-id="ba5b1-145">Avanmäl anpassade rekommendationer</span><span class="sxs-lookup"><span data-stu-id="ba5b1-145">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="ba5b1-146">Aktivera rekommendationer för "köp liknande produkter"</span><span class="sxs-lookup"><span data-stu-id="ba5b1-146">Enable "shop similar looks" recommendations</span></span>](shop-similar-looks.md)

[<span data-ttu-id="ba5b1-147">Lägga till produktrekommendationer i POS</span><span class="sxs-lookup"><span data-stu-id="ba5b1-147">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="ba5b1-148">Lägg till rekommendationer på transaktionsskärmen</span><span class="sxs-lookup"><span data-stu-id="ba5b1-148">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="ba5b1-149">Justera rekommendationsresultat från AI-ML</span><span class="sxs-lookup"><span data-stu-id="ba5b1-149">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="ba5b1-150">Skapa granskade rekommendationer manuellt</span><span class="sxs-lookup"><span data-stu-id="ba5b1-150">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="ba5b1-151">Skapa rekommendationer med demodata</span><span class="sxs-lookup"><span data-stu-id="ba5b1-151">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)

[<span data-ttu-id="ba5b1-152">Vanliga frågor om produktrekommendationer</span><span class="sxs-lookup"><span data-stu-id="ba5b1-152">Product recommendations FAQ</span></span>](faq-recommendations.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
