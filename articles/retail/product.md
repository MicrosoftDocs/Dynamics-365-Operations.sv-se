---
title: Produktrekommendationer i kassa
description: I det här avsnittet beskrivs användning av produktrekommendationer för en försäljningsenhet (POS).
author: bebeale
manager: AnnBe
ms.date: 10/01/19
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 259664
ms.assetid: 5dd8db08-cd96-4f7e-9e65-b05ca815d580
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: c78fc1f2f1bb08d01828a8b71ad5d3c16ad31b86
ms.sourcegitcommit: 5b53bdafa5cb9a1279576bfece0452a50383b122
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/01/2019
ms.locfileid: "2278400"
---
# <a name="product-recommendations-on-pos"></a><span data-ttu-id="b41a1-103">Produktrekommendationer i kassa</span><span class="sxs-lookup"><span data-stu-id="b41a1-103">Product recommendations on POS</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="b41a1-104">I grund och botten är produktrekommendationerna ett omvandlande affärsprogram som sträcker sig över alla detaljhandelsytor för att skapa omfattande, spännande och skräddarsydda produktidentifieringsupplevelser.</span><span class="sxs-lookup"><span data-stu-id="b41a1-104">At its core, product Recommendations are a transformative business application that span across all retail spaces to create rich, engaging, and tailored product discovery experiences.</span></span> <span data-ttu-id="b41a1-105">Om du vill använda den här funktionen i kassan följer du stegen i [hur du lägger till rekommendationer i kassaenheterna.](add-recommendations-control-pos-screen.md)</span><span class="sxs-lookup"><span data-stu-id="b41a1-105">To implement this feature on POS, follow the steps on [how to add recommendations to your POS devices.](add-recommendations-control-pos-screen.md)</span></span> 

<span data-ttu-id="b41a1-106">Mer information om funktioner för produktrekommendationer finns i [produktrekommendationer - översikt.](../commerce/product-recommendations.md)</span><span class="sxs-lookup"><span data-stu-id="b41a1-106">For more information about product recommendations features, read the [product recommendations overview.](../commerce/product-recommendations.md)</span></span> 

## <a name="scenarios"></a><span data-ttu-id="b41a1-107">Scenarier</span><span class="sxs-lookup"><span data-stu-id="b41a1-107">Scenarios</span></span>

<span data-ttu-id="b41a1-108">Produktrekommendationer har aktiverats för följande kassascenarier.</span><span class="sxs-lookup"><span data-stu-id="b41a1-108">Product recommendations are enabled for the following POS scenarios.</span></span> <span data-ttu-id="b41a1-109">De är tillgängliga i Cloud POS och Modern POS (MPOS).</span><span class="sxs-lookup"><span data-stu-id="b41a1-109">They are available in Cloud POS or Modern POS (MPOS).</span></span>

1. <span data-ttu-id="b41a1-110">På sidan **Produktdetaljer**:</span><span class="sxs-lookup"><span data-stu-id="b41a1-110">On the **Product details** page:</span></span>

    - <span data-ttu-id="b41a1-111">• Om en butiksmedarbetare besöker en sida **Produktdetaljer** när han eller hon tittar på föregående transaktioner via olika kanaler, föreslår rekommendationstjänsten ytterligare artiklar som kan köpas tillsammans.</span><span class="sxs-lookup"><span data-stu-id="b41a1-111">• If a store associate visits a **Product details** page when looking at previous transactions across different channels, the recommendations service suggests additional items that are likely to be purchased together.</span></span>

    <span data-ttu-id="b41a1-112">[![Rekommendationer på sidan produktinformation](./media/proddetails.png)](./media/proddetails.png)</span><span class="sxs-lookup"><span data-stu-id="b41a1-112">[![Recommendations on the Product details page](./media/proddetails.png)](./media/proddetails.png)</span></span>

2. <span data-ttu-id="b41a1-113">På sidan **Transaktion**:</span><span class="sxs-lookup"><span data-stu-id="b41a1-113">On the **Transaction** page:</span></span>

    - <span data-ttu-id="b41a1-114">• I rekommendationsmotorn föreslås objekt baserat på hela listan över artiklar i korgen som ofta köps ihop.</span><span class="sxs-lookup"><span data-stu-id="b41a1-114">• The recommendation engine suggests items based on the entire list of items in the basket that are frequently bought together.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b41a1-115">För att kunna visa rekommendationer på sidan **Transaktion** måste återförsäljaren uppdatera skärmlayouten i Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="b41a1-115">To display recommendations on the **Transaction** page, the retailer needs to update the screen layout in Dynamics 365 for Retail.</span></span> <span data-ttu-id="b41a1-116">Kontrollen **Rekommendationer** måste tas bort på sidan **Transaktion**.</span><span class="sxs-lookup"><span data-stu-id="b41a1-116">The **Recommendations** control must be dropped onto the **Transaction** page.</span></span>

    <span data-ttu-id="b41a1-117">[![Rekommendationer på sidan Transaktion](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)</span><span class="sxs-lookup"><span data-stu-id="b41a1-117">[![Recommendations on the Transaction page](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)</span></span>

## <a name="configure-dynamics-365-retail-to-enable-pos-recommendations"></a><span data-ttu-id="b41a1-118">Konfigurera Dynamics 365 Retail för att aktivera rekommendationer i kassa</span><span class="sxs-lookup"><span data-stu-id="b41a1-118">Configure Dynamics 365 Retail to enable POS recommendations</span></span>

<span data-ttu-id="b41a1-119">Så här ställs produktrekommendationer in:</span><span class="sxs-lookup"><span data-stu-id="b41a1-119">To set up product recommendations, follow these steps:</span></span>

1. <span data-ttu-id="b41a1-120">Se till att tjänsten har uppdaterats till **10.0.6 version.**</span><span class="sxs-lookup"><span data-stu-id="b41a1-120">Ensure your service has been updated to the **10.0.6 build.**</span></span>
2. <span data-ttu-id="b41a1-121">Följ instruktionerna om hur du [aktiverar produktrekommendationer](../commerce/enable-product-recommendations.md) för ditt företag.</span><span class="sxs-lookup"><span data-stu-id="b41a1-121">Follow the instructions on how to [enable product recommendations](../commerce/enable-product-recommendations.md) for your business.</span></span>
3. <span data-ttu-id="b41a1-122">Tillval; Om du vill visa rekommendationer på transaktionsskärmen, gå då till **Skärmlayout**, välj din skärmlayout, starta **Designer för skrämlayout**, och släpp sedan kontrollen **Rekommendationer** där så behövs.</span><span class="sxs-lookup"><span data-stu-id="b41a1-122">Optional: To display recommendations on the transaction screen, go to **Screen Layout**, choose your screen layout, launch the **Screen layout designer**, and then drop the **recommendations** control where needed.</span></span>
4. <span data-ttu-id="b41a1-123">Gå till **Detaljhandelsparametrar**, välj **Maskininlärning** och välj **Ja** under **Aktivera kassarekommendationer**.</span><span class="sxs-lookup"><span data-stu-id="b41a1-123">Go to **Retail parameters**, select **Machine-learning**, select **Yes** under **Enable POS recommendations**.</span></span>
5. <span data-ttu-id="b41a1-124">Kör jobbet **1110** för global konfiguration om du vill se rekommendationer på kassan.</span><span class="sxs-lookup"><span data-stu-id="b41a1-124">To see recommendations on POS, run global configuration job **1110**.</span></span> <span data-ttu-id="b41a1-125">Kör kanalkonfigurationsjobbet **1070** för att avspeglar ändringar i kassaskärmens layoutdesigner.</span><span class="sxs-lookup"><span data-stu-id="b41a1-125">To reflect changes made to POS screen layout designer, run channel configuration job **1070**.</span></span>



## <a name="troubleshoot-issues-where-you-have-product-recommendations-already-enabled"></a><span data-ttu-id="b41a1-126">Felsök problem där du redan produktrekommendationer aktiverade</span><span class="sxs-lookup"><span data-stu-id="b41a1-126">Troubleshoot issues where you have Product recommendations already enabled</span></span>

- <span data-ttu-id="b41a1-127">Gå till **Butiksparametrar** \> **Rekommendationslistor** \> **Inaktivera produktrekommendationer** och kör **Globalt konfigurationsjobb \[9999\]**.</span><span class="sxs-lookup"><span data-stu-id="b41a1-127">Navigate to **Retail Parameters** \> **Recommendation lists** \> **Disable product recommendations** and run **Global configuration job \[9999\]**.</span></span> 
- <span data-ttu-id="b41a1-128">Om du har lagt till **rekommendationskontroll** till din transaktionsskärm med **Layoutdesigner för skärm**, ta även bort den.</span><span class="sxs-lookup"><span data-stu-id="b41a1-128">If you added the **Recommendations control** to your transaction screen using the **Screen layout designer**, please remove that as well.</span></span>
- <span data-ttu-id="b41a1-129">Om du har fler frågor läser du [Vanliga frågor om rekommendationer](../commerce/faq-recommendations.md) för mer information.</span><span class="sxs-lookup"><span data-stu-id="b41a1-129">If you have additional questions, check out the [Recommendations FAQ](../commerce/faq-recommendations.md) for more information.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b41a1-130">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="b41a1-130">Additional resources</span></span>

<span data-ttu-id="b41a1-131">[Lägg till en rekommendationskontroll på transaktionssidan på en kassaenhet](add-recommendations-control-pos-screen.md)
[Produktrekommendationer - översikt](../commerce/product-recommendations.md)
[Aktivera produktrekommendationer](../commerce/enable-product-recommendations.md)</span><span class="sxs-lookup"><span data-stu-id="b41a1-131">[Add a recommendations control to the transaction page on a POS device](add-recommendations-control-pos-screen.md)
[Product recommendations overview](../commerce/product-recommendations.md)
[Enable product recommendations](../commerce/enable-product-recommendations.md)</span></span> 
