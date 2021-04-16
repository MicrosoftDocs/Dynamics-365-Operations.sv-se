---
title: Lägg till produktrekommendationer i POS
description: I det här avsnittet beskrivs användning av produktrekommendationer för en försäljningsenhet (POS).
author: bebeale
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailParameters
audience: Application User
ms.reviewer: josaw
ms.custom: 259664
ms.assetid: 5dd8db08-cd96-4f7e-9e65-b05ca815d580
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: a1a25e3d5bc1cc5c1c7509186451fdfef50dd6cf
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5792349"
---
# <a name="add-product-recommendations-on-pos"></a><span data-ttu-id="507ca-103">Lägg till produktrekommendationer i POS</span><span class="sxs-lookup"><span data-stu-id="507ca-103">Add product recommendations on POS</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="507ca-104">I grund och botten är produktrekommendationerna ett omvandlande affärsprogram som sträcker sig över alla handelsytor för att skapa omfattande, spännande och skräddarsydda produktidentifieringsupplevelser.</span><span class="sxs-lookup"><span data-stu-id="507ca-104">At its core, product recommendations are a transformative business application that span across all commerce spaces to create rich, engaging, and tailored product discovery experiences.</span></span> <span data-ttu-id="507ca-105">Om du vill använda den här funktionen i POS följer du stegen i [hur du lägger till rekommendationer i kassaenheterna.](add-recommendations-control-pos-screen.md)</span><span class="sxs-lookup"><span data-stu-id="507ca-105">To implement this feature on POS, follow the steps on [how to add recommendations to your POS devices.](add-recommendations-control-pos-screen.md)</span></span> 

<span data-ttu-id="507ca-106">Mer information om funktioner för produktrekommendationer finns i [produktrekommendationer – översikt.](../commerce/product-recommendations.md)</span><span class="sxs-lookup"><span data-stu-id="507ca-106">For more information about product recommendations features, read the [product recommendations overview.](../commerce/product-recommendations.md)</span></span> 

## <a name="scenarios"></a><span data-ttu-id="507ca-107">Scenarier</span><span class="sxs-lookup"><span data-stu-id="507ca-107">Scenarios</span></span>

<span data-ttu-id="507ca-108">Produktrekommendationer har aktiverats för följande kassascenarier.</span><span class="sxs-lookup"><span data-stu-id="507ca-108">Product recommendations are enabled for the following POS scenarios.</span></span> <span data-ttu-id="507ca-109">De är tillgängliga i Cloud POS och Modern POS (MPOS).</span><span class="sxs-lookup"><span data-stu-id="507ca-109">They are available in Cloud POS or Modern POS (MPOS).</span></span>

1. <span data-ttu-id="507ca-110">På sidan **Produktdetaljer**:</span><span class="sxs-lookup"><span data-stu-id="507ca-110">On the **Product details** page:</span></span>

    - <span data-ttu-id="507ca-111">Om en butiksmedarbetare besöker en sida **Produktdetaljer** när han eller hon tittar på föregående transaktioner via olika kanaler, föreslår rekommendationstjänsten ytterligare artiklar som kan köpas tillsammans.</span><span class="sxs-lookup"><span data-stu-id="507ca-111">If a store associate visits a **Product details** page when looking at previous transactions across different channels, the recommendations service suggests additional items that are likely to be purchased together.</span></span>

    <span data-ttu-id="507ca-112">[![Rekommendationer på sidan produktinformation](./media/proddetails.png)](./media/proddetails.png)</span><span class="sxs-lookup"><span data-stu-id="507ca-112">[![Recommendations on the Product details page](./media/proddetails.png)](./media/proddetails.png)</span></span>

2. <span data-ttu-id="507ca-113">På sidan **Transaktion**:</span><span class="sxs-lookup"><span data-stu-id="507ca-113">On the **Transaction** page:</span></span>

    - <span data-ttu-id="507ca-114">I rekommendationsmotorn föreslås objekt baserat på hela listan över artiklar i korgen som ofta köps ihop.</span><span class="sxs-lookup"><span data-stu-id="507ca-114">The recommendation engine suggests items based on the entire list of items in the basket that are frequently bought together.</span></span>

    > [!NOTE]
    > <span data-ttu-id="507ca-115">För att kunna visa rekommendationer på sidan **Transaktion** måste återförsäljaren uppdatera skärmlayouten i Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="507ca-115">To display recommendations on the **Transaction** page, the retailer needs to update the screen layout in Dynamics 365 Commerce.</span></span> <span data-ttu-id="507ca-116">Kontrollen **Rekommendationer** måste tas bort på sidan **Transaktion**.</span><span class="sxs-lookup"><span data-stu-id="507ca-116">The **Recommendations** control must be dropped onto the **Transaction** page.</span></span>

    <span data-ttu-id="507ca-117">[![Rekommendationer på sidan Transaktion](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)</span><span class="sxs-lookup"><span data-stu-id="507ca-117">[![Recommendations on the Transaction page](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)</span></span>

## <a name="configure-commerce-to-enable-pos-recommendations"></a><span data-ttu-id="507ca-118">Konfigurera Commerce för att aktivera rekommendationer i kassa</span><span class="sxs-lookup"><span data-stu-id="507ca-118">Configure Commerce to enable POS recommendations</span></span>

<span data-ttu-id="507ca-119">Så här ställs produktrekommendationer in:</span><span class="sxs-lookup"><span data-stu-id="507ca-119">To set up product recommendations, follow these steps:</span></span>

1. <span data-ttu-id="507ca-120">Se till att tjänsten har uppdaterats till **10.0.6 version.**</span><span class="sxs-lookup"><span data-stu-id="507ca-120">Ensure your service has been updated to the **10.0.6 build.**</span></span>
2. <span data-ttu-id="507ca-121">Följ instruktionerna om hur du [aktiverar produktrekommendationer](../commerce/enable-product-recommendations.md) för ditt företag.</span><span class="sxs-lookup"><span data-stu-id="507ca-121">Follow the instructions on how to [enable product recommendations](../commerce/enable-product-recommendations.md) for your business.</span></span>
3. <span data-ttu-id="507ca-122">Tillval; Om du vill visa rekommendationer på transaktionsskärmen, gå då till **Skärmlayout**, välj din skärmlayout, starta **Designer för skrämlayout**, och släpp sedan kontrollen **Rekommendationer** där så behövs.</span><span class="sxs-lookup"><span data-stu-id="507ca-122">Optional: To display recommendations on the transaction screen, go to **Screen Layout**, choose your screen layout, launch the **Screen layout designer**, and then drop the **recommendations** control where needed.</span></span>
4. <span data-ttu-id="507ca-123">Gå till **Handelsparametrar**, välj **Maskininlärning** och välj **Ja** under **Aktivera kassarekommendationer**.</span><span class="sxs-lookup"><span data-stu-id="507ca-123">Go to **Commerce parameters**, select **Machine-learning**, select **Yes** under **Enable POS recommendations**.</span></span>
5. <span data-ttu-id="507ca-124">Kör jobbet **1110** för global konfiguration om du vill se rekommendationer på POS.</span><span class="sxs-lookup"><span data-stu-id="507ca-124">To see recommendations on POS, run global configuration job **1110**.</span></span> <span data-ttu-id="507ca-125">Kör kanalkonfigurationsjobbet **1070** för att avspeglar ändringar i kassaskärmens layoutdesigner.</span><span class="sxs-lookup"><span data-stu-id="507ca-125">To reflect changes made to POS screen layout designer, run channel configuration job **1070**.</span></span>

## <a name="troubleshoot-issues-where-you-have-product-recommendations-already-enabled"></a><span data-ttu-id="507ca-126">Felsök problem där du redan produktrekommendationer aktiverade</span><span class="sxs-lookup"><span data-stu-id="507ca-126">Troubleshoot issues where you have Product recommendations already enabled</span></span>

- <span data-ttu-id="507ca-127">Gå till **Handelsparametrar** \> **Rekommendationslistor** \> **Inaktivera produktrekommendationer** och kör **Globalt konfigurationsjobb \[9999\]**.</span><span class="sxs-lookup"><span data-stu-id="507ca-127">Navigate to **Commerce Parameters** \> **Recommendation lists** \> **Disable product recommendations** and run **Global configuration job \[9999\]**.</span></span> 
- <span data-ttu-id="507ca-128">Om du har lagt till **rekommendationskontroll** till din transaktionsskärm med **Layoutdesigner för skärm**, ta även bort den.</span><span class="sxs-lookup"><span data-stu-id="507ca-128">If you added the **Recommendations control** to your transaction screen using the **Screen layout designer**, please remove that as well.</span></span>
- <span data-ttu-id="507ca-129">Om du har fler frågor läser du [Vanliga frågor om produktrekommendationer](../commerce/faq-recommendations.md) för mer information.</span><span class="sxs-lookup"><span data-stu-id="507ca-129">If you have additional questions, check out the [Product recommendations FAQ](../commerce/faq-recommendations.md) for more information.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="507ca-130">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="507ca-130">Additional resources</span></span>

[<span data-ttu-id="507ca-131">Översikt av produktrekommendationer</span><span class="sxs-lookup"><span data-stu-id="507ca-131">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="507ca-132">Aktivera Azure Data Lake Storage i en Dynamics 365 Commerce-miljö</span><span class="sxs-lookup"><span data-stu-id="507ca-132">Enable Azure Data Lake Storage in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="507ca-133">Aktivera produktrekommendationer</span><span class="sxs-lookup"><span data-stu-id="507ca-133">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="507ca-134">Aktivera anpassade rekommendationer</span><span class="sxs-lookup"><span data-stu-id="507ca-134">Enable personalized recommendations</span></span>](personalized-recommendations.md)

[<span data-ttu-id="507ca-135">Avanmäl anpassade rekommendationer</span><span class="sxs-lookup"><span data-stu-id="507ca-135">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="507ca-136">Aktivera rekommendationer för "köp liknande produkter"</span><span class="sxs-lookup"><span data-stu-id="507ca-136">Enable "shop similar looks" recommendations</span></span>](shop-similar-looks.md)

[<span data-ttu-id="507ca-137">Lägg till rekommendationer på transaktionsskärmen</span><span class="sxs-lookup"><span data-stu-id="507ca-137">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="507ca-138">Justera rekommendationsresultat från AI-ML</span><span class="sxs-lookup"><span data-stu-id="507ca-138">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="507ca-139">Skapa granskade rekommendationer manuellt</span><span class="sxs-lookup"><span data-stu-id="507ca-139">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="507ca-140">Skapa rekommendationer med demodata</span><span class="sxs-lookup"><span data-stu-id="507ca-140">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)

[<span data-ttu-id="507ca-141">Vanliga frågor om produktrekommendationer</span><span class="sxs-lookup"><span data-stu-id="507ca-141">Product recommendations FAQ</span></span>](faq-recommendations.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]