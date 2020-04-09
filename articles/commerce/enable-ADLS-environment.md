---
title: Aktivera ADLS i en Dynamics 365 Commerce-miljö
description: I det här avsnittet beskrivs hur du aktiverar och testar Azure Data Lake Storage (ADLS) för en Dynamics 365 Commerce-miljö, vilket är en förutsättning för att du ska kunna aktivera produktrekommendationer.
author: bebeale
manager: AnnBe
ms.date: 03/19/2020
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
ms.openlocfilehash: 3c037f5603af5af84917084eefa1edd508891c0d
ms.sourcegitcommit: de5af1912201dd70aa85fdcad0b184c42405802e
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/21/2020
ms.locfileid: "3154446"
---
# <a name="enable-adls-in-a-dynamics-365-commerce-environment"></a><span data-ttu-id="56ade-103">Aktivera ADLS i en Dynamics 365 Commerce-miljö</span><span class="sxs-lookup"><span data-stu-id="56ade-103">Enable ADLS in a Dynamics 365 Commerce environment</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="56ade-104">I det här avsnittet beskrivs hur du aktiverar och testar Azure Data Lake Storage (ADLS) för en Dynamics 365 Commerce-miljö, vilket är en förutsättning för att du ska kunna aktivera produktrekommendationer.</span><span class="sxs-lookup"><span data-stu-id="56ade-104">This topic explains how to enable and test Azure Data Lake Storage (ADLS) for a Dynamics 365 Commerce environment, which is a prerequisite for enabling product recommendations.</span></span>

## <a name="overview"></a><span data-ttu-id="56ade-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="56ade-105">Overview</span></span>

<span data-ttu-id="56ade-106">I Dynamics 365 Commerce-lösningen spåras all produktinformation och all transaktionsinformation i miljöns enhetsarkiv.</span><span class="sxs-lookup"><span data-stu-id="56ade-106">In the Dynamics 365 Commerce solution, all product and transaction information is tracked in the environment's Entity store.</span></span> <span data-ttu-id="56ade-107">Om du vill göra dessa data tillgängliga för andra Dynamics 365-tjänster, t.ex. dataanalyser, affärsstrategier och anpassade rekommendationer, måste du ansluta miljön till en kundägd Azure Data Lake Storage Gen 2 (ADLS)-lösning.</span><span class="sxs-lookup"><span data-stu-id="56ade-107">To make this data accessible to other Dynamics 365 services, such as data analytics, business intelligence, and personalized recommendations, it is necessary to connect the environment to a customer-owned Azure Data Lake Storage Gen 2 (ADLS) solution.</span></span>

<span data-ttu-id="56ade-108">Eftersom ADLS konfigureras i en miljö, speglas alla nödvändiga data från enhetsarkivet samtidigt som de skyddas och kontrolleras av kunden.</span><span class="sxs-lookup"><span data-stu-id="56ade-108">As ADLS is configured in an environment, all necessary data is mirrored from the Entity store while still being protected and under customer's control.</span></span>

<span data-ttu-id="56ade-109">Om produktrekommendationer eller anpassade rekommendationer också har aktiverats i miljön ger produktrekommendationerna stack åtkomst till den dedikerade mappen i ADLS för att hämta kundens data och beräkna rekommendationer baserat på den.</span><span class="sxs-lookup"><span data-stu-id="56ade-109">If product recommendations or personalized recommendations are also enabled in the environment, then the product recommendations stack will be granted access to the dedicated folder in ADLS to retrieve the customer’s data and compute recommendations based on it.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="56ade-110">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="56ade-110">Prerequisites</span></span>

<span data-ttu-id="56ade-111">Kunder måste ha ADLS konfigurerat i en Azure-prenumeration som de äger.</span><span class="sxs-lookup"><span data-stu-id="56ade-111">Customers need to have ADLS configured in an Azure subscription that they own.</span></span> <span data-ttu-id="56ade-112">Det här avsnittet behandlar inte köp av en Azure-prenumeration eller inställningen av ett ADLS-aktiverat lagringskonto.</span><span class="sxs-lookup"><span data-stu-id="56ade-112">This topic does not cover the purchase of an Azure subscription or the setup of an ADLS-enabled storage account.</span></span>

<span data-ttu-id="56ade-113">Mer information om ADLS finns i [officiell ADLS-dokumentation](https://azure.microsoft.com/pricing/details/storage/data-lake).</span><span class="sxs-lookup"><span data-stu-id="56ade-113">For more information about ADLS, see [ADLS official documentation](https://azure.microsoft.com/pricing/details/storage/data-lake).</span></span>
  
## <a name="configuration-steps"></a><span data-ttu-id="56ade-114">Konfigurationssteg</span><span class="sxs-lookup"><span data-stu-id="56ade-114">Configuration steps</span></span>

<span data-ttu-id="56ade-115">I det här avsnittet beskrivs de konfigurationssteg som krävs för att aktivera ADLS i en miljö.</span><span class="sxs-lookup"><span data-stu-id="56ade-115">This section covers the configuration steps necessary for enabling ADLS in an environment.</span></span>

### <a name="enable-adls-in-the-environment"></a><span data-ttu-id="56ade-116">Aktivera ADLS i miljö</span><span class="sxs-lookup"><span data-stu-id="56ade-116">Enable ADLS in the environment</span></span>

1. <span data-ttu-id="56ade-117">Logga in på miljöns backoffice-Portal.</span><span class="sxs-lookup"><span data-stu-id="56ade-117">Log in to the environment's back office portal.</span></span>
1. <span data-ttu-id="56ade-118">Sök efter **Systemparametrar** och navigera till fliken **Dataanslutningar**.</span><span class="sxs-lookup"><span data-stu-id="56ade-118">Search for **System Parameters** and navigate to the **Data connections** tab.</span></span> 
1. <span data-ttu-id="56ade-119">Ange **Aktivera Data Lake-integrering** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="56ade-119">Set **Enable Data Lake integration** to **Yes**.</span></span>
1. <span data-ttu-id="56ade-120">Ange **Indroppning uppdatering av Data Lake** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="56ade-120">Set **Trickle update Data Lake** to **Yes**.</span></span>
1. <span data-ttu-id="56ade-121">Ange sedan följande obligatorisk information:</span><span class="sxs-lookup"><span data-stu-id="56ade-121">Next, enter the following required information:</span></span>
    1. <span data-ttu-id="56ade-122">**Program-ID** // **Programhemlighet** // **DNS-namn** - Behövs för att ansluta till KeyVault där ADLS-hemligheten lagras.</span><span class="sxs-lookup"><span data-stu-id="56ade-122">**Application ID** // **Application Secret** // **DNS Name** - Needed to connect to KeyVault where the ADLS secret is stored.</span></span>
    1. <span data-ttu-id="56ade-123">**Hemligtnamn** - Det hemliga namnet lagrat i KeyVault och används för att autentisera med ADLS.</span><span class="sxs-lookup"><span data-stu-id="56ade-123">**Secret name** - The secret name stored in KeyVault and used to authenticate with ADLS.</span></span>
1. <span data-ttu-id="56ade-124">Spara ändringarna i det övre vänstra hörnet på sidan.</span><span class="sxs-lookup"><span data-stu-id="56ade-124">Save your changes in the top left corner of the page.</span></span>

<span data-ttu-id="56ade-125">I bilden nedan visas ett exempel på ADLS-konfiguration.</span><span class="sxs-lookup"><span data-stu-id="56ade-125">The following image shows an example ADLS configuration.</span></span>

![Exempel på ADLS-konfiguration](./media/exampleADLSConfig1.png)

### <a name="test-the-adls-connection"></a><span data-ttu-id="56ade-127">Testa ADLS-anslutningen</span><span class="sxs-lookup"><span data-stu-id="56ade-127">Test the ADLS connection</span></span>

1. <span data-ttu-id="56ade-128">Testa anslutningen till KeyVault med hjälp länk **Testa Azure Key Vault**.</span><span class="sxs-lookup"><span data-stu-id="56ade-128">Test the connection to KeyVault using the **Test Azure Key Vault** link.</span></span>
1. <span data-ttu-id="56ade-129">Testa anslutningen till ett ADLS med hjälp länk **Testa Azure Storage**.</span><span class="sxs-lookup"><span data-stu-id="56ade-129">Test the connection to ADLS using the **Test Azure Storage** link.</span></span>

> [!NOTE]
> <span data-ttu-id="56ade-130">Om testerna misslyckas kontrollerar du att all KeyVault-information som lagts till ovan är korrekt och försöker igen.</span><span class="sxs-lookup"><span data-stu-id="56ade-130">If the tests fail, double-check that all of the KeyVault information added above is correct, then try again.</span></span>

<span data-ttu-id="56ade-131">När anslutningstesten har lyckats måste du aktivera automatisk uppdatering för enhetsarkivet.</span><span class="sxs-lookup"><span data-stu-id="56ade-131">Once the connection tests are successful, you must enable automatic refresh for Entity store.</span></span>

<span data-ttu-id="56ade-132">Aktivera automatisk uppdatering för enhetsarkivet genom att följa stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="56ade-132">To enable automatic refresh for Entity store, follow these steps.</span></span>

1. <span data-ttu-id="56ade-133">Sök efter **enhetsarkiv**.</span><span class="sxs-lookup"><span data-stu-id="56ade-133">Search for **Entity Store**.</span></span>
1. <span data-ttu-id="56ade-134">Navigera till listan till vänster till enhet **RetailSales** och välj **redigera**.</span><span class="sxs-lookup"><span data-stu-id="56ade-134">In the list on the left, navigate to the **RetailSales** entry, and select **Edit**.</span></span>
1. <span data-ttu-id="56ade-135">Se till **Automatisk uppdatering är aktiverat** är inställd på **Ja**, välj **Uppdatera** och välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="56ade-135">Ensure that **Automatic Refresh Enabled** is set to **Yes**, select **Refresh**, and then select **Save**.</span></span>

<span data-ttu-id="56ade-136">I bilden nedan visas ett exempel på ett enhetslagring med automatisk uppdatering aktiverat.</span><span class="sxs-lookup"><span data-stu-id="56ade-136">The following image shows an example of Entity store with automatic refresh enabled.</span></span>

![Exempel på enhetslagring med automatisk uppdatering aktiverad](./media/exampleADLSConfig2.png)

<span data-ttu-id="56ade-138">ADLS har nu konfigurerats för miljön.</span><span class="sxs-lookup"><span data-stu-id="56ade-138">ADLS is now configured for the environment.</span></span> 

<span data-ttu-id="56ade-139">Om det inte redan är klart följer du stegen för [aktivera produktrekommendationer och anpassning](enable-product-recommendations.md) för miljön.</span><span class="sxs-lookup"><span data-stu-id="56ade-139">If not completed already, follow the steps for [enabling product recommendations and personalization](enable-product-recommendations.md) for the environment.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="56ade-140">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="56ade-140">Additional resources</span></span>

[<span data-ttu-id="56ade-141">Översikt av produktrekommendationer</span><span class="sxs-lookup"><span data-stu-id="56ade-141">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="56ade-142">Aktivera produktrekommendationer</span><span class="sxs-lookup"><span data-stu-id="56ade-142">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="56ade-143">Aktivera anpassade rekommendationer</span><span class="sxs-lookup"><span data-stu-id="56ade-143">Enable personalized recommendations</span></span>](personalized-recommendations.md)

[<span data-ttu-id="56ade-144">Avanmäl anpassade rekommendationer</span><span class="sxs-lookup"><span data-stu-id="56ade-144">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="56ade-145">Lägg till produktrekommendationer i kassan</span><span class="sxs-lookup"><span data-stu-id="56ade-145">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="56ade-146">Lägg till rekommendationer på transaktionsskärmen</span><span class="sxs-lookup"><span data-stu-id="56ade-146">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="56ade-147">Justera rekommendationsresultat från AI-ML</span><span class="sxs-lookup"><span data-stu-id="56ade-147">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="56ade-148">Skapa granskade rekommendationer manuellt</span><span class="sxs-lookup"><span data-stu-id="56ade-148">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="56ade-149">Skapa rekommendationer med demodata</span><span class="sxs-lookup"><span data-stu-id="56ade-149">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)

[<span data-ttu-id="56ade-150">Vanliga frågor om produktrekommendationer</span><span class="sxs-lookup"><span data-stu-id="56ade-150">Product recommendations FAQ</span></span>](faq-recommendations.md)


