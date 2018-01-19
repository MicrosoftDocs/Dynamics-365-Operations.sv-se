---
title: "Översikt över anpassade produktrekommendationer"
description: "Det här avsnittet innehåller information om produktrekommendationer fra Dynamics 365 for Retail som kan visas på kassaenheten."
author: ashishmsft
manager: AnnBe
ms.date: 11/14/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
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
ms.translationtype: HT
ms.sourcegitcommit: ceea24519d641c676521771cee274feb64ca7783
ms.openlocfilehash: fde7face188bbfd3bfdf66fbff81969f75704302
ms.contentlocale: sv-se
ms.lasthandoff: 01/19/2018

---

# <a name="personalized-product-recommendations-overview"></a><span data-ttu-id="07131-103">Översikt över anpassade produktrekommendationer</span><span class="sxs-lookup"><span data-stu-id="07131-103">Personalized product recommendations overview</span></span>

[!include[banner](includes/banner.md)]


> [!NOTE]
> <span data-ttu-id="07131-104">Denna funktion finns i dagsläget endast för begränsade distributionstopologier samt distributionstopologier för produktion (hög tillgänglighet).</span><span class="sxs-lookup"><span data-stu-id="07131-104">This feature is currently available on sandbox and production (high-availability) deployment topologies only.</span></span> 

<span data-ttu-id="07131-105">I Dynamics 365 for Retail kan produktrekommendationerna visas på kassaenheten.</span><span class="sxs-lookup"><span data-stu-id="07131-105">In Dynamics 365 for Retail, product recommendations can be displayed on the point of sale (POS) device.</span></span> <span data-ttu-id="07131-106">Rekommendationerna är artiklar som kunden kan vara intresserad av baserat på sina tidigare inköp, artiklar i önskelistor samt artiklar som andra kunder köpt online och i fysiska butiker.</span><span class="sxs-lookup"><span data-stu-id="07131-106">The recommendations are items that the customer might be interested in based on their purchase history, items in their wish list, and items that other customers purchased online and in brick-and-mortar stores.</span></span> <span data-ttu-id="07131-107">För återförsäljare med stora kataloger hjälper rekommendationer kunden att identifiera produkter.</span><span class="sxs-lookup"><span data-stu-id="07131-107">For retailers with large catalogs, recommendations help the customer with product discovery.</span></span> <span data-ttu-id="07131-108">Genom att visa upp produkter riktade till en kunds intresse och inköpsvanor kan produktrekommendationer hjälpa återförsäljare med merförsäljning och korsförsäljning, och förbättrad kundvård.</span><span class="sxs-lookup"><span data-stu-id="07131-108">By showcasing products targeted to a customer’s interests and buying habits, product recommendations can help retailers with up-sell and cross-sell, and can enhance customer retention.</span></span> <span data-ttu-id="07131-109">I Dynamics 365 for Retail drivs produktrekommendationerna genom kognitiva tjänster och Microsoft Azure-maskininlärning.</span><span class="sxs-lookup"><span data-stu-id="07131-109">In Dynamics 365 for Retail, product recommendations are powered by cognitive services and Microsoft Azure machine learning.</span></span>


<a name="scenarios"></a><span data-ttu-id="07131-110">Scenarier</span><span class="sxs-lookup"><span data-stu-id="07131-110">Scenarios</span></span>
---------

<span data-ttu-id="07131-111">Produktrekommendationer har aktiverats för följande kassascenarier.</span><span class="sxs-lookup"><span data-stu-id="07131-111">Product recommendations are enabled for the following POS scenarios.</span></span> <span data-ttu-id="07131-112">De är tillgängliga i Cloud POS och Modern POS (MPOS).</span><span class="sxs-lookup"><span data-stu-id="07131-112">They are available in Cloud POS or Modern POS (MPOS).</span></span>

1.  <span data-ttu-id="07131-113">På sidan **Produktdetaljer**:</span><span class="sxs-lookup"><span data-stu-id="07131-113">On the **Product details** page:</span></span>

-   <span data-ttu-id="07131-114">Om en butiksmedarbetare besöker en sida **Produktdetaljer** när han eller hon tittar på föregående transaktioner via olika kanaler, föreslår rekommendationsmotorn ytterligare artiklar som kan köpas tillsammans.</span><span class="sxs-lookup"><span data-stu-id="07131-114">If a store associate visits a **Product details** page when looking at previous transactions across different channels, the recommendation engine suggests additional items that are likely to be purchased together.</span></span>
-   <span data-ttu-id="07131-115">Om butiksmedarbetaren lägger till en kund i transaktionen och sedan besöker en **Produktdetaljer**-sida ger rekommendationsmotorn personliga rekommendationer som gjorts på kundens transaktionshistorik.</span><span class="sxs-lookup"><span data-stu-id="07131-115">If the store associate adds a customer to the transaction and then visits a **Product details** page, the recommendation engine provides personalized recommendations using the customer's transaction history.</span></span>

<span data-ttu-id="07131-116">[![proddetails](./media/proddetails.png)](./media/proddetails.png)</span><span class="sxs-lookup"><span data-stu-id="07131-116">[![proddetails](./media/proddetails.png)](./media/proddetails.png)</span></span>

2.  <span data-ttu-id="07131-117">På sidan **Transaktion**:</span><span class="sxs-lookup"><span data-stu-id="07131-117">On the **Transaction** page:</span></span>

-   <span data-ttu-id="07131-118">Rekommendationsmotorn föreslår artiklar baserat på hela listan över artiklar i varukorgen.</span><span class="sxs-lookup"><span data-stu-id="07131-118">The recommendation engine suggests items based on the entire list of items in the basket.</span></span>
-   <span data-ttu-id="07131-119">Om butiksmedarbetaren lägger till en kund i transaktionen, ger rekommendationsmotorn personliga rekommendationer som gjorts på kundens transaktionshistorik och listan med artiklar i varukorgen.</span><span class="sxs-lookup"><span data-stu-id="07131-119">If the store associate adds a customer to the transaction, the recommendation engine provides personal recommendations using the customer’s transaction history and the list of items in the basket.</span></span>

> [!NOTE]
> <span data-ttu-id="07131-120">Återförsäljaren måste uppdatera skrämlayouten i Dynamics 365 for Retail för att kunna visa rekommendationer på sidan **Transaktion**.</span><span class="sxs-lookup"><span data-stu-id="07131-120">To display recommendations on the **Transaction** page, the retailer needs to update the screen layout in Dynamics 365 for Retail.</span></span> <span data-ttu-id="07131-121">Kontrollen **Rekommendationer** måste tas bort på sidan **Transaktion**.</span><span class="sxs-lookup"><span data-stu-id="07131-121">The **Recommendations** control must be dropped on to the **Transaction** page.</span></span> <span data-ttu-id="07131-122">[![transactionscreenmultipleproductslargemessengersbag-5](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)</span><span class="sxs-lookup"><span data-stu-id="07131-122">[![transactionscreenmultipleproductslargemessengersbag-5](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)</span></span>

3.  <span data-ttu-id="07131-123">På sidan **Kundinformation**:</span><span class="sxs-lookup"><span data-stu-id="07131-123">On the **Customer details** page:</span></span>
    -   <span data-ttu-id="07131-124">Rekommendationsmotorn föreslår artiklar baserat på användar-ID och artiklar i kundens önskelista.</span><span class="sxs-lookup"><span data-stu-id="07131-124">The recommendation engine suggests items based on the user ID and items in the customer’s wish list.</span></span>

<span data-ttu-id="07131-125">[![customerdetailsrecommendations](./media/customerdetailsrecommendations.png)](./media/customerdetailsrecommendations.png)</span><span class="sxs-lookup"><span data-stu-id="07131-125">[![customerdetailsrecommendations](./media/customerdetailsrecommendations.png)](./media/customerdetailsrecommendations.png)</span></span>

## <a name="configure-dynamics-365-for-retail-to-enable-pos-recommendations"></a><span data-ttu-id="07131-126">Konfigurera Dynamics 365 for Retail för att aktivera kassarekommendationer</span><span class="sxs-lookup"><span data-stu-id="07131-126">Configure Dynamics 365 for Retail to enable POS recommendations</span></span>
<span data-ttu-id="07131-127">För att ställa in produktrekommendationer måste du göra följande.</span><span class="sxs-lookup"><span data-stu-id="07131-127">To set up product recommendations, you need to do the following.</span></span>

1.  <span data-ttu-id="07131-128">Kontrollera att du har valt rätt **Juridisk person**.</span><span class="sxs-lookup"><span data-stu-id="07131-128">Make sure that you have selected the correct **Legal entity**.</span></span>
2.  <span data-ttu-id="07131-129">Gå till **Enhetsbutiken**markerar du **Butiksförsäljning** och klickar sedan på **Uppdatera**.</span><span class="sxs-lookup"><span data-stu-id="07131-129">Navigate to **Entity store**, select **Retail sales**, and then click **Refresh**.</span></span> <span data-ttu-id="07131-130">Detta använder demonstrationsdata (eller data) från databasen fungerar och flytta den till enbutiken för enhetslagring.</span><span class="sxs-lookup"><span data-stu-id="07131-130">This will use the demo data (or your data) from your operational database and move it to Entity store.</span></span>
3.  <span data-ttu-id="07131-131">Tillval; Om du vill visa rekommendationer på transaktionsskärmen, gå då till **Skärmlayout**, välj din skärmlayout, starta **Designer för skrämlayout**, och släpp sedan kontrollen **Rekommendationer** där så behövs.</span><span class="sxs-lookup"><span data-stu-id="07131-131">Optional: To display recommendations on the transaction screen, go to **Screen Layout**, choose your screen layout, launch the **Screen layout designer**, and then drop the **recommendations** control where needed.</span></span>

4.  <span data-ttu-id="07131-132">Gå till **Detaljhandelsparametrar**, välj **Maskininlärning** och välj **Ja** under **Aktivera kassarekommendationer**.</span><span class="sxs-lookup"><span data-stu-id="07131-132">Go to **Retail parameters**, select **Machine-learning**, select **Yes** under **Enable POS recommendations**.</span></span>
5.  <span data-ttu-id="07131-133">Kör jobbet **1110** för global konfiguration om du vill se rekommendationer på kassan.</span><span class="sxs-lookup"><span data-stu-id="07131-133">To see recommendations on POS, run global configuration job **1110**.</span></span> <span data-ttu-id="07131-134">Kör kanalkonfigurationsjobbet **1070** för att avspeglar ändringar i kassaskärmens layoutdesigner.</span><span class="sxs-lookup"><span data-stu-id="07131-134">To reflect changes made to POS screen layout designer, run channel configuration job **1070**.</span></span>

## <a name="how-does-it-work"></a><span data-ttu-id="07131-135">[]()Hur fungerar det?</span><span class="sxs-lookup"><span data-stu-id="07131-135">[]()How does it work?</span></span>
<span data-ttu-id="07131-136">När du uppdaterar **Enhetslagring**-enheten utförs följande åtgärder.</span><span class="sxs-lookup"><span data-stu-id="07131-136">When you refresh the **Entity store** entity, the following actions take place.</span></span>

-   <span data-ttu-id="07131-137">Data i det format som krävs av kognitiva tjänster extraheras från Dynamics 365 for Retails driftsdatabas och skickas till enhetslagringen.</span><span class="sxs-lookup"><span data-stu-id="07131-137">Data in the format required by the Cognitive services is extracted from the Dynamics 365 for Retail operational database and sent to the Entity store.</span></span>
-   <span data-ttu-id="07131-138">Informationen används av Azure Data Factory (ADF) för att rensa data med hjälp av Hive-skript som en del av ADM-aktiviteter.</span><span class="sxs-lookup"><span data-stu-id="07131-138">The data is used by Azure Data Factory (ADF) to cleanse the data using Hive scripts as part of ADF activities.</span></span> <span data-ttu-id="07131-139">Rensade data lagras i blobb-lagring.</span><span class="sxs-lookup"><span data-stu-id="07131-139">Cleansed data is stored in blob storage.</span></span>
-   <span data-ttu-id="07131-140">Data från blobb-lagring används av API för kognitiva tjänster för att utbilda en rekommendationsmodell.</span><span class="sxs-lookup"><span data-stu-id="07131-140">Data from blob storage is used by the Cognitive services API to train a recommendation model.</span></span>

<span data-ttu-id="07131-141">När du har aktiverat **Aktivera rekommendationer** och kör konfigurationsjobb, utförs följande åtgärder.</span><span class="sxs-lookup"><span data-stu-id="07131-141">When you turn on **Enable recommendations** and run the configuration jobs, the following actions take place.</span></span>

-   <span data-ttu-id="07131-142">Modellautentiseringsuppgifter och -ID hämtas från API och lagras i Dynamics 365 for Retails driftsdatabas, i web.config för AOS, och även i butiksservern.</span><span class="sxs-lookup"><span data-stu-id="07131-142">Model credentials and ID are picked up from the API and stored in the Dynamics 365 for Retail operational database, in the web.config for AOS, and also in the retail server.</span></span>
-   <span data-ttu-id="07131-143">Modellautentiseringsuppgifter och -ID görs tillgängliga för CRT så att anrop för produktrekommendationer från Cloud POS och MOPS i onlineläge kan utföras.</span><span class="sxs-lookup"><span data-stu-id="07131-143">Model credentials and ID are made available to CRT so that calls for product recommendations from Cloud POS and MPOS in online mode can be honored.</span></span>


<a name="see-also"></a><span data-ttu-id="07131-144">Se även</span><span class="sxs-lookup"><span data-stu-id="07131-144">See also</span></span>
--------

[<span data-ttu-id="07131-145">Lägg till en rekommendationskontroll på transaktionssidan på en kassaenhet</span><span class="sxs-lookup"><span data-stu-id="07131-145">Add a recommendations control to the transaction page on a POS device</span></span>](add-recommendations-control-pos-screen.md)




