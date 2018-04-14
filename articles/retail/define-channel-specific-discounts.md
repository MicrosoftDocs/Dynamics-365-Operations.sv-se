---
title: Definiera kanalspecifika rabatter
description: "Återförsäljare ställer ofta in olika rabatter i olika kanaler. Det här avsnittet behandlar de koncept du behöver känna till för att skapa en rabatt för en viss kanal."
author: scott-tucker
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailAffiliationPriceGroup, RetailCatalogPriceGroup, RetailChannelPriceGroup, RetailDiscountPriceGroup, RetailDiscountPricingWorkspace, RetailPeriodicDiscount, RetailStoreItemPriceList, RetailStoreTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 16401
ms.assetid: d807fd51-86aa-47a0-8e00-6c5ddd21ff6b
ms.search.region: global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 34039b298e8994e50a7c06ef034698e8c1264389
ms.contentlocale: sv-se
ms.lasthandoff: 04/13/2018

---

# <a name="define-channel-specific-discounts"></a><span data-ttu-id="9336a-104">Definiera kanalspecifika rabatter</span><span class="sxs-lookup"><span data-stu-id="9336a-104">Define channel-specific discounts</span></span>

[!INCLUDE [banner](includes/banner.md)]

<span data-ttu-id="9336a-105">Återförsäljare ställer ofta in olika rabatter i olika kanaler.</span><span class="sxs-lookup"><span data-stu-id="9336a-105">Retailers often set different discounts in different channels.</span></span> <span data-ttu-id="9336a-106">Det här avsnittet behandlar de koncept du behöver känna till för att skapa en rabatt för en viss kanal.</span><span class="sxs-lookup"><span data-stu-id="9336a-106">This topic reviews the concepts you need to know to create a discount for a specific channel.</span></span> 

<a name="channel-specific-discounts"></a><span data-ttu-id="9336a-107">Kanalspecifika rabatter</span><span class="sxs-lookup"><span data-stu-id="9336a-107">Channel-specific discounts</span></span>
--------------------------

<span data-ttu-id="9336a-108">Återförsäljare erbjuder ofta olika rabatter i olika kanaler.</span><span class="sxs-lookup"><span data-stu-id="9336a-108">Retailers often offer different discounts in different channels.</span></span> <span data-ttu-id="9336a-109">Detta kan bero på att man vill adressera lokala marknadsvillkor eller hantera konkurrerande återförsäljare.</span><span class="sxs-lookup"><span data-stu-id="9336a-109">This is may be done to address local market conditions or to deal with competing retailers.</span></span>

<span data-ttu-id="9336a-110">Microsoft Dynamics 365 for Retail använder prisgrupper för att definiera kanalspecifika rabatter.</span><span class="sxs-lookup"><span data-stu-id="9336a-110">Microsoft Dynamics 365 for Retail uses price groups to define channel-specific discounts.</span></span> <span data-ttu-id="9336a-111">Prisgrupper kan tilldelas till en eller flera av följande enheter: kanaler, kataloger, anknytningar och bonusprogram.</span><span class="sxs-lookup"><span data-stu-id="9336a-111">Price groups can be assigned to one or more of the following entities: channels, catalogs, affiliations, and loyalty programs.</span></span> <span data-ttu-id="9336a-112">Den här artikeln diskuterar kanaler, men samma koncept gäller för katalograbatter, anknytningsrabatter och lojalitetsrabatter.</span><span class="sxs-lookup"><span data-stu-id="9336a-112">This article discusses channels, but the same concepts apply to catalog discounts, affiliations discounts, and loyalty discounts.</span></span>

## <a name="price-groups"></a><span data-ttu-id="9336a-113">Prisgrupper</span><span class="sxs-lookup"><span data-stu-id="9336a-113">Price groups</span></span>

<span data-ttu-id="9336a-114">[![Prisgrupper](./media/price-groups-1024x608.png)](./media/price-groups.png)</span><span class="sxs-lookup"><span data-stu-id="9336a-114">[![Price groups](./media/price-groups-1024x608.png)](./media/price-groups.png)</span></span>

<span data-ttu-id="9336a-115">Diagrammet ovan visar relationen mellan enheter som kan göras för en transaktion (kanal, katalog, anknytning, kund, bonuskort) och de olika rabattyper som kan konfigureras.</span><span class="sxs-lookup"><span data-stu-id="9336a-115">The diagram above illustrates the relationship between entities that may be on a transaction (channel, catalog, affiliation, customer, loyalty card) and the various discount types that can be configured.</span></span> <span data-ttu-id="9336a-116">Alla transaktioner uppstår i en kanal, varför kanalen garanterat finns med i en transaktion.</span><span class="sxs-lookup"><span data-stu-id="9336a-116">All transactions occur in a channel, so the channel is guaranteed to be present on a transaction.</span></span> <span data-ttu-id="9336a-117">De återstående enheterna är valfria.</span><span class="sxs-lookup"><span data-stu-id="9336a-117">The remaining entities are optional.</span></span> <span data-ttu-id="9336a-118">På varje huvuddatasida finns en länk till en relaterad prisgruppssida där du kan visa och lägga till prisgrupper efter behov.</span><span class="sxs-lookup"><span data-stu-id="9336a-118">On each master data pages there is a link to a related price groups page where you can view and add price groups as needed.</span></span> <span data-ttu-id="9336a-119">En prisgrupp används för koppling av fyra olika typer av enheter till rabatter, prisjusteringar och handelsavtal.</span><span class="sxs-lookup"><span data-stu-id="9336a-119">A price group is used to relate four different types of entities to discounts, price adjustments, and trade agreements.</span></span> <span data-ttu-id="9336a-120">Vi rekommenderar att du planerar en strategi för hur du ska namnge dina prisgrupper för att hålla ordning på dem.</span><span class="sxs-lookup"><span data-stu-id="9336a-120">We recommend that you plan a strategy for how you will name your price groups to keep them organized.</span></span> <span data-ttu-id="9336a-121">Ett alternativ är att använda ett bokstavs- eller sifferprefix/-suffix för att skilja mellan de olika typerna.</span><span class="sxs-lookup"><span data-stu-id="9336a-121">One option would be to use a letter or number prefix or suffix to distinguish between the different types.</span></span> <span data-ttu-id="9336a-122">Exempelvis 1-xxxxx för kanal prisgrupper och 2-xxxxx för katalogprisgrupper.</span><span class="sxs-lookup"><span data-stu-id="9336a-122">For example, 1-xxxxx for channel price groups and 2-xxxxx for catalog price groups.</span></span> <span data-ttu-id="9336a-123">Det finns fyra förfrågningssidor som fokuserar på var och en av återförsäljarenheterna som kan ha associerade rabatter.</span><span class="sxs-lookup"><span data-stu-id="9336a-123">There are four inquiry pages that focus on each of the retail entities that can have discounts associated to them.</span></span>

-   <span data-ttu-id="9336a-124">**Prisgrupper för butikskanal**– På den här sidan visas en lista med kanaler och rabatter som är länkade för varje prisgrupp.</span><span class="sxs-lookup"><span data-stu-id="9336a-124">**Retail channel price groups** - This page shows a list of channels and discounts linked together for each price group.</span></span>
-   <span data-ttu-id="9336a-125">**Katalogprisgrupper**– På den här sidan visas en lista med kataloger och rabatter som är länkade för varje prisgrupp.</span><span class="sxs-lookup"><span data-stu-id="9336a-125">**Catalog price groups** - This page shows a list of catalogs and discounts linked together for each price group.</span></span>
-   <span data-ttu-id="9336a-126">**Bonusprisgrupper**– På den här sidan visas en lista med bonusprogram och rabatter som är länkade för varje prisgrupp.</span><span class="sxs-lookup"><span data-stu-id="9336a-126">**Loyalty price groups** - This page shows a list of loyalty programs and discounts linked together for each price group.</span></span>
-   <span data-ttu-id="9336a-127">**Anknytningsprisgrupper**– På den här sidan visas en lista med anknytningar och rabatter som är länkade för varje prisgrupp.</span><span class="sxs-lookup"><span data-stu-id="9336a-127">**Affiliation price groups** - This page shows a list of affiliations and discounts linked together for each price group.</span></span>

## <a name="example-channel-discount-set-up"></a><span data-ttu-id="9336a-128">Inställningar för exempelkanalrabatt</span><span class="sxs-lookup"><span data-stu-id="9336a-128">Example channel discount set up</span></span>
<span data-ttu-id="9336a-129">Följande exempel illustrerar uppgifterna som ingår i konfigurationen av en kanalrabatt.</span><span class="sxs-lookup"><span data-stu-id="9336a-129">The following example illustrates the tasks involved in setting up a channel discount.</span></span>

1.  <span data-ttu-id="9336a-130">För det här exemplet har du en kanal kallad **Houston**, och du ska skapa en ny rabatt kallad **Back-to-School**.</span><span class="sxs-lookup"><span data-stu-id="9336a-130">For this example, you have a channel called **Houston**, and you're going to create a new discount called **Back-to-School.**</span></span>
2.  <span data-ttu-id="9336a-131">Eftersom prissättnings- och rabattstrategin inkluderar möjligheten till kanalrabatter skapar du alltid en kanalspecifik prisgrupp när du skapar en kanal.</span><span class="sxs-lookup"><span data-stu-id="9336a-131">Because the pricing and discount strategy includes the possibility of channel discounts, you always create a channel-specific price group when you create a channel.</span></span>
3.  <span data-ttu-id="9336a-132">Du har prisgruppen **Houston-PG** och den är tilldelad kanalen **Houston**.</span><span class="sxs-lookup"><span data-stu-id="9336a-132">You have the price group **Houston-PG** and it is assigned to the **Houston** channel.</span></span>
4.  <span data-ttu-id="9336a-133">När du har skapat den nya rabatten **Back-to-School** måste du klicka på **Prisgrupper** längst upp på sidan **Rabatt**.</span><span class="sxs-lookup"><span data-stu-id="9336a-133">After you create the new **Back-to-School** discount, you need to click **Price groups** on the top of the **Discount** page.</span></span> <span data-ttu-id="9336a-134">Sidan **Rabattprisgrupper** öppnas.</span><span class="sxs-lookup"><span data-stu-id="9336a-134">The **Discount price groups** page will open.</span></span> <span data-ttu-id="9336a-135">Välj **Nytt** och välj prisgruppen **Houston-PG**.</span><span class="sxs-lookup"><span data-stu-id="9336a-135">Next, click **New** and select the **Houston-PG** price group.</span></span>
5.  <span data-ttu-id="9336a-136">Nu kan du aktivera rabatten och flytta den till kanalen.</span><span class="sxs-lookup"><span data-stu-id="9336a-136">Now you can enable the discount and push it to the channel.</span></span>



<a name="see-also"></a><span data-ttu-id="9336a-137">Se även</span><span class="sxs-lookup"><span data-stu-id="9336a-137">See also</span></span>
--------

[<span data-ttu-id="9336a-138">Prisjusteringar och rabatter</span><span class="sxs-lookup"><span data-stu-id="9336a-138">Price adjustments and discounts</span></span>](price-adjustments-discounts.md)




