---
title: Definiera kanalspecifika rabatter
description: Återförsäljare ställer ofta in olika rabatter i olika kanaler. Det här avsnittet behandlar de koncept du behöver känna till för att skapa en rabatt för en viss kanal.
author: scott-tucker
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailAffiliationPriceGroup, RetailCatalogPriceGroup, RetailChannelPriceGroup, RetailDiscountPriceGroup, RetailDiscountPricingWorkspace, RetailPeriodicDiscount, RetailStoreItemPriceList, RetailStoreTable
audience: Application User
ms.reviewer: josaw
ms.custom: 16401
ms.assetid: d807fd51-86aa-47a0-8e00-6c5ddd21ff6b
ms.search.region: global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 990c0d0b4b89420094dc86552b3e07717e5c7056
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4991400"
---
# <a name="define-channel-specific-discounts"></a><span data-ttu-id="062e7-104">Definiera kanalspecifika rabatter</span><span class="sxs-lookup"><span data-stu-id="062e7-104">Define channel-specific discounts</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="062e7-105">Det här avsnittet behandlar de koncept du behöver känna till för att skapa en rabatt för en viss kanal.</span><span class="sxs-lookup"><span data-stu-id="062e7-105">This topic reviews the concepts you need to know to create a discount for a specific channel.</span></span>

## <a name="channel-specific-discounts"></a><span data-ttu-id="062e7-106">Kanalspecifika rabatter</span><span class="sxs-lookup"><span data-stu-id="062e7-106">Channel-specific discounts</span></span>

<span data-ttu-id="062e7-107">Återförsäljare erbjuder ofta olika rabatter i olika kanaler.</span><span class="sxs-lookup"><span data-stu-id="062e7-107">Retailers often offer different discounts in different channels.</span></span> <span data-ttu-id="062e7-108">Detta kan bero på att man vill adressera lokala marknadsvillkor eller hantera konkurrerande återförsäljare.</span><span class="sxs-lookup"><span data-stu-id="062e7-108">This may be done to address local market conditions or to deal with competing retailers.</span></span>

<span data-ttu-id="062e7-109">Commerce använder prisgrupper för att definiera kanalspecifika rabatter.</span><span class="sxs-lookup"><span data-stu-id="062e7-109">Commerce uses price groups to define channel-specific discounts.</span></span> <span data-ttu-id="062e7-110">Prisgrupper kan tilldelas till en eller flera av följande enheter: kanaler, kataloger, anknytningar och bonusprogram.</span><span class="sxs-lookup"><span data-stu-id="062e7-110">Price groups can be assigned to one or more of the following entities: channels, catalogs, affiliations, and loyalty programs.</span></span> <span data-ttu-id="062e7-111">Den här artikeln diskuterar kanaler, men samma koncept gäller för katalograbatter, anknytningsrabatter och lojalitetsrabatter.</span><span class="sxs-lookup"><span data-stu-id="062e7-111">This article discusses channels, but the same concepts apply to catalog discounts, affiliations discounts, and loyalty discounts.</span></span>

## <a name="price-groups"></a><span data-ttu-id="062e7-112">Prisgrupper</span><span class="sxs-lookup"><span data-stu-id="062e7-112">Price groups</span></span>

<span data-ttu-id="062e7-113">[![Prisgrupper](./media/price-groups-1024x608.png)](./media/price-groups.png)</span><span class="sxs-lookup"><span data-stu-id="062e7-113">[![Price groups](./media/price-groups-1024x608.png)](./media/price-groups.png)</span></span>

<span data-ttu-id="062e7-114">Diagrammet ovan visar relationen mellan enheter som kan göras för en transaktion (kanal, katalog, anknytning, kund, bonuskort) och de olika rabattyper som kan konfigureras.</span><span class="sxs-lookup"><span data-stu-id="062e7-114">The diagram above illustrates the relationship between entities that may be on a transaction (channel, catalog, affiliation, customer, loyalty card) and the various discount types that can be configured.</span></span> <span data-ttu-id="062e7-115">Alla transaktioner uppstår i en kanal, varför kanalen garanterat finns med i en transaktion.</span><span class="sxs-lookup"><span data-stu-id="062e7-115">All transactions occur in a channel, so the channel is guaranteed to be present on a transaction.</span></span> <span data-ttu-id="062e7-116">De återstående enheterna är valfria.</span><span class="sxs-lookup"><span data-stu-id="062e7-116">The remaining entities are optional.</span></span> <span data-ttu-id="062e7-117">På varje huvuddatasida finns en länk till en relaterad prisgruppssida där du kan visa och lägga till prisgrupper efter behov.</span><span class="sxs-lookup"><span data-stu-id="062e7-117">On each master data pages there is a link to a related price groups page where you can view and add price groups as needed.</span></span> <span data-ttu-id="062e7-118">En prisgrupp används för koppling av fyra olika typer av enheter till rabatter, prisjusteringar och handelsavtal.</span><span class="sxs-lookup"><span data-stu-id="062e7-118">A price group is used to relate four different types of entities to discounts, price adjustments, and trade agreements.</span></span> <span data-ttu-id="062e7-119">Vi rekommenderar att du planerar en strategi för hur du ska namnge dina prisgrupper för att hålla ordning på dem.</span><span class="sxs-lookup"><span data-stu-id="062e7-119">We recommend that you plan a strategy for how you will name your price groups to keep them organized.</span></span> <span data-ttu-id="062e7-120">Ett alternativ är att använda ett bokstavs- eller sifferprefix/-suffix för att skilja mellan de olika typerna.</span><span class="sxs-lookup"><span data-stu-id="062e7-120">One option would be to use a letter or number prefix or suffix to distinguish between the different types.</span></span> <span data-ttu-id="062e7-121">Exempelvis 1-xxxxx för kanal prisgrupper och 2-xxxxx för katalogprisgrupper.</span><span class="sxs-lookup"><span data-stu-id="062e7-121">For example, 1-xxxxx for channel price groups and 2-xxxxx for catalog price groups.</span></span> <span data-ttu-id="062e7-122">Det finns fyra förfrågningssidor som fokuserar på var och en av handelsenheterna som kan ha associerade rabatter.</span><span class="sxs-lookup"><span data-stu-id="062e7-122">There are four inquiry pages that focus on each of the commerce entities that can have discounts associated to them.</span></span>

- <span data-ttu-id="062e7-123">**Prisgrupper för kanal** – På den här sidan visas en lista med kanaler och rabatter som är länkade för varje prisgrupp.</span><span class="sxs-lookup"><span data-stu-id="062e7-123">**Channel channel price groups** – This page shows a list of channels and discounts linked together for each price group.</span></span>
- <span data-ttu-id="062e7-124">**Katalogprisgrupper** – På den här sidan visas en lista med kataloger och rabatter som är länkade för varje prisgrupp.</span><span class="sxs-lookup"><span data-stu-id="062e7-124">**Catalog price groups** – This page shows a list of catalogs and discounts linked together for each price group.</span></span>
- <span data-ttu-id="062e7-125">**Bonusprisgrupper** – På den här sidan visas en lista med bonusprogram och rabatter som är länkade för varje prisgrupp.</span><span class="sxs-lookup"><span data-stu-id="062e7-125">**Loyalty price groups** – This page shows a list of loyalty programs and discounts linked together for each price group.</span></span>
- <span data-ttu-id="062e7-126">**Anknytningsprisgrupper** – På den här sidan visas en lista med anknytningar och rabatter som är länkade för varje prisgrupp.</span><span class="sxs-lookup"><span data-stu-id="062e7-126">**Affiliation price groups** – This page shows a list of affiliations and discounts linked together for each price group.</span></span>

## <a name="example-channel-discount-set-up"></a><span data-ttu-id="062e7-127">Inställningar för exempelkanalrabatt</span><span class="sxs-lookup"><span data-stu-id="062e7-127">Example channel discount set up</span></span>

<span data-ttu-id="062e7-128">Följande exempel illustrerar uppgifterna som ingår i konfigurationen av en kanalrabatt.</span><span class="sxs-lookup"><span data-stu-id="062e7-128">The following example illustrates the tasks involved in setting up a channel discount.</span></span>

1. <span data-ttu-id="062e7-129">För det  här exemplet har du en kanal kallad **Houston**, och du ska skapa en ny rabatt kallad **Back-to-School**.</span><span class="sxs-lookup"><span data-stu-id="062e7-129">For this example, you have a channel called **Houston**, and you're going to create a new discount called **Back-to-School**.</span></span>
2. <span data-ttu-id="062e7-130">Eftersom prissättnings- och rabattstrategin inkluderar möjligheten till kanalrabatter skapar du alltid en kanalspecifik prisgrupp när du skapar en kanal.</span><span class="sxs-lookup"><span data-stu-id="062e7-130">Because the pricing and discount strategy includes the possibility of channel discounts, you always create a channel-specific price group when you create a channel.</span></span>
3. <span data-ttu-id="062e7-131">Du har prisgruppen **Houston-PG** och den är tilldelad kanalen **Houston**.</span><span class="sxs-lookup"><span data-stu-id="062e7-131">You have the price group **Houston-PG** and it is assigned to the **Houston** channel.</span></span>
4. <span data-ttu-id="062e7-132">När du har skapat den nya rabatten **Back-to-School** måste du klicka på **Prisgrupper** längst upp på sidan **Rabatt**.</span><span class="sxs-lookup"><span data-stu-id="062e7-132">After you create the new **Back-to-School** discount, you need to click **Price groups** on the top of the **Discount** page.</span></span> <span data-ttu-id="062e7-133">Sidan **Rabattprisgrupper** öppnas.</span><span class="sxs-lookup"><span data-stu-id="062e7-133">The **Discount price groups** page will open.</span></span> <span data-ttu-id="062e7-134">Välj **Nytt** och välj prisgruppen **Houston-PG**.</span><span class="sxs-lookup"><span data-stu-id="062e7-134">Next, click **New** and select the **Houston-PG** price group.</span></span>
5. <span data-ttu-id="062e7-135">Nu kan du aktivera rabatten och flytta den till kanalen.</span><span class="sxs-lookup"><span data-stu-id="062e7-135">Now you can enable the discount and push it to the channel.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="062e7-136">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="062e7-136">Additional resources</span></span>

[<span data-ttu-id="062e7-137">Prisjusteringar och rabatter</span><span class="sxs-lookup"><span data-stu-id="062e7-137">Price adjustments and discounts</span></span>](price-adjustments-discounts.md)
