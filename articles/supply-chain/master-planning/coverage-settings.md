---
title: Disponeringsinställningar
description: Det här ämnet ger information om de disponeringsinställningar som huvudplaneringen använder för att beräkna artikelbehov.
author: roxanadiaconu
manager: AnnBe
ms.date: 09/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqGroup, ReqItemTable, ReqItemTableWizard
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2494
ms.assetid: 5a95ae4f-ca75-47d9-a1c3-68c97b42f166
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3a63184852751bb65fb7e80d721f8c48fd847609
ms.sourcegitcommit: edfd805356894710488ce07cb1c89313f448b222
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/16/2019
ms.locfileid: "1998981"
---
# <a name="coverage-settings"></a><span data-ttu-id="d52ea-103">Disponeringsinställningar</span><span class="sxs-lookup"><span data-stu-id="d52ea-103">Coverage settings</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d52ea-104">Under huvudplanering används disponeringsinställningar för att beräkna artikelbehov.</span><span class="sxs-lookup"><span data-stu-id="d52ea-104">Master scheduling uses coverage settings to calculate item requirements.</span></span>

<span data-ttu-id="d52ea-105">Du kan ange disponeringsinställningar på flera sätt:</span><span class="sxs-lookup"><span data-stu-id="d52ea-105">You can specify coverage settings in several ways:</span></span>

- <span data-ttu-id="d52ea-106">Ange disponeringsinställningar för en disponeringsgrupp.</span><span class="sxs-lookup"><span data-stu-id="d52ea-106">Specify coverage settings for a coverage group.</span></span>

    <span data-ttu-id="d52ea-107">Du kan skapa en disponeringsgrupp som innehåller inställningar för alla produkter som är länkade till disponeringsgruppen.</span><span class="sxs-lookup"><span data-stu-id="d52ea-107">You can create a coverage group that contains settings for all products that are linked to the coverage group.</span></span> <span data-ttu-id="d52ea-108">För att skapa en täckningsgrupp, gå till **huvudplanering &gt; Inställningar &gt; Disponering &gt; Disponeringsgrupper**.</span><span class="sxs-lookup"><span data-stu-id="d52ea-108">To create a coverage group, go to **Master planning &gt; Setup &gt; Coverage &gt; Coverage groups**.</span></span> <span data-ttu-id="d52ea-109">Du kan koppla en disponeringsgrupp till en produkt.</span><span class="sxs-lookup"><span data-stu-id="d52ea-109">You can link a coverage group to a product.</span></span> <span data-ttu-id="d52ea-110">Om länken är specifik för en plats, ett lagerställe eller en produktdimension, ska du använda fältet **Disponeringsgrupp** på sidan **Artikeldisponering**.</span><span class="sxs-lookup"><span data-stu-id="d52ea-110">If the link is specific to a site, warehouse, or product dimension, use the **Coverage group** field on the **Item coverage** page.</span></span> <span data-ttu-id="d52ea-111">Om länken är allmänn, oavsett produktdimensionerna, använder du fältet **Disponeringsgrupp** på snabbfliken **Planera** på sidan **Produktdetaljer** sidan.</span><span class="sxs-lookup"><span data-stu-id="d52ea-111">If the link is generic, regardless of the product dimensions, use the **Coverage group** field on the **Plan** FastTab of the **Product details** page.</span></span> <span data-ttu-id="d52ea-112">Som standard, om du inte länkar en täckningsgrupp till en produkt, använder du huvudplaneringen av den allmänna täckningsgruppen som anges på **Huvudplaneringsparametrar**.</span><span class="sxs-lookup"><span data-stu-id="d52ea-112">By default, if you don't link a coverage group to a product, master planning uses the general coverage group that is specified on the **Master planning parameters** page.</span></span>

- <span data-ttu-id="d52ea-113">Ange disponeringsinställningar för en produkt.</span><span class="sxs-lookup"><span data-stu-id="d52ea-113">Specify coverage settings for a product.</span></span>

    <span data-ttu-id="d52ea-114">Du kan skapa disponeringsinställningar för en specifik produkt.</span><span class="sxs-lookup"><span data-stu-id="d52ea-114">You can create coverage settings for a specific product.</span></span> <span data-ttu-id="d52ea-115">Gå till **Produktinformationshantering &gt; Produkter &gt; Frisläppta produkter**.</span><span class="sxs-lookup"><span data-stu-id="d52ea-115">Go to **Product information management &gt; Products &gt; Released products**.</span></span> <span data-ttu-id="d52ea-116">Välj produkt och gå sedan till Åtgärdsfönster, på fliken **Plan** i grupp **Disponering** och klicka på **Artikeldisponering** för att öppna sidan **Artikeldisponering**.</span><span class="sxs-lookup"><span data-stu-id="d52ea-116">Select the product, and then, on the Action Pane, on the **Plan** tab, in the **Coverage** group, select **Item coverage** to open the **Item coverage** page.</span></span> <span data-ttu-id="d52ea-117">Om produkten redan är länkad till en disponeringsgrupp kan du åsidosätta inställningarna för gruppen med hjälp av fältet **Åsidosätt**.</span><span class="sxs-lookup"><span data-stu-id="d52ea-117">If the product is already linked to a coverage group, you can override the coverage group settings by using the **Override** field.</span></span> <span data-ttu-id="d52ea-118">Disponeringinställningarna på sidan**Artikeldisponering** åsidosätter inställningarna på sidan **Disponeringsgrupp**.</span><span class="sxs-lookup"><span data-stu-id="d52ea-118">The coverage settings on the **Item coverage** page take precedence over the settings on the **Coverage group** page.</span></span>

- <span data-ttu-id="d52ea-119">Ange disponeringsinställningar för en produkt med hjälp av en guide.</span><span class="sxs-lookup"><span data-stu-id="d52ea-119">Specify coverage settings for a product by using a wizard.</span></span>

    <span data-ttu-id="d52ea-120">Guiden hjälper dig steg för steg genom processen att ställa in de primära parametrarna för artikeldisponering.</span><span class="sxs-lookup"><span data-stu-id="d52ea-120">The wizard guides you step by step through the process of setting up the primary item coverage parameters.</span></span> <span data-ttu-id="d52ea-121">På åtgärdssidan **Artikeldisponering** klickar du på **Guide** om du vill öppna **Artikeldisponeringsguiden**.</span><span class="sxs-lookup"><span data-stu-id="d52ea-121">On the **Item coverage** page, on the Action Pane, select **Wizard** to open the **Item Coverage Wizard**.</span></span>

- <span data-ttu-id="d52ea-122">Ange disponeringsinställningar för en dimensionsgrupp.</span><span class="sxs-lookup"><span data-stu-id="d52ea-122">Specify coverage settings for a dimension group.</span></span>

    <span data-ttu-id="d52ea-123">Gå till **Produktinformationshantering &gt; Produkter &gt; Frisläppta produkter**.</span><span class="sxs-lookup"><span data-stu-id="d52ea-123">Go to **Product information management &gt; Products &gt; Released products**.</span></span> <span data-ttu-id="d52ea-124">På sidan **Frisläppt produktdetalj** på snabbfliken **Allmänt** i avsnittet **Administration** klickar du på länken i fältet **Lagringsdimensionsgrupp**.</span><span class="sxs-lookup"><span data-stu-id="d52ea-124">On the **Released product details** page, on the **General** FastTab, in the **Administration** section, select the link in the **Storage dimension group** field.</span></span> <span data-ttu-id="d52ea-125">På fältet **Lagringsdimensionsgrupper** markerar du fältet **Disponera per dimension** om du vill skapa disponeringsinställningar för en dimension i lagringsdimensiongruppen.</span><span class="sxs-lookup"><span data-stu-id="d52ea-125">On the **Storage dimension groups** page, select the **Coverage plan by dimension** check box to create the coverage settings for a dimension in the storage dimension group.</span></span> <span data-ttu-id="d52ea-126">Fält **Disponera per dimension** måste väljas för alla produktdimensioner, t.ex. konfiguration, färg, storlek och stil.</span><span class="sxs-lookup"><span data-stu-id="d52ea-126">The **Coverage plan by dimension** field must be selected for all product dimensions, such as configuration, color, size, and style.</span></span>


## <a name="coverage-codes"></a><span data-ttu-id="d52ea-127">Täckningskoder</span><span class="sxs-lookup"><span data-stu-id="d52ea-127">Coverage codes</span></span>

<span data-ttu-id="d52ea-128">Huvudplanering kan konfigureras till att använda olika återanskaffningsmetoder.</span><span class="sxs-lookup"><span data-stu-id="d52ea-128">Master planning can be configured to use different replenishment methods.</span></span> <span data-ttu-id="d52ea-129">Återanskaffningsmetoderna eller partistorleksmetoderna är de tekniker som används i systemet för att fastställa partistorleken för inköpta eller producerade artiklar.</span><span class="sxs-lookup"><span data-stu-id="d52ea-129">The replenishment methods or lot-sizing methods are the techniques used by the system to determine the batch size for purchased or produced items.</span></span> 

<span data-ttu-id="d52ea-130">Varje återanskaffningsmetod tilldelas en av följande täckningskoder:</span><span class="sxs-lookup"><span data-stu-id="d52ea-130">Each replenishment method is assigned one of the following coverage codes:</span></span>

- <span data-ttu-id="d52ea-131">**Manuell** - Metoden för partistorlek där systemet inte föreslår inköps-, överförings- eller tillverkningsorder för artikeln.</span><span class="sxs-lookup"><span data-stu-id="d52ea-131">**Manual** - The lot-sizing method where the system does not suggest purchased, transfer, or production orders for the item.</span></span> <span data-ttu-id="d52ea-132">Planeraren för artikeln ansvarar för att skapa de nödvändiga orderna för påfyllnaden av artikeln.</span><span class="sxs-lookup"><span data-stu-id="d52ea-132">The planner for the item will be in charge of creating the required orders for the replenishment of the item.</span></span>
- <span data-ttu-id="d52ea-133">**Per behov** - Den partistorleksmetod i vilken systemet skapar en planerad inköps-, överförings- eller produktionsorder per behov för artikeln.</span><span class="sxs-lookup"><span data-stu-id="d52ea-133">**Per requirement** - The lot-sizing method in which the system creates a planned purchase, transfer, or production order per requirement for the item.</span></span> <span data-ttu-id="d52ea-134">Detta används vanligtvis för dyra artiklar med återkommande efterfrågan.</span><span class="sxs-lookup"><span data-stu-id="d52ea-134">This is generally used for expensive items with intermittent demand.</span></span>  
- <span data-ttu-id="d52ea-135">**Per period** - den partistorleksmetod som kombinerar hela efter frågan för en period till en order för artikeln.</span><span class="sxs-lookup"><span data-stu-id="d52ea-135">**Per period** - The lot-sizing method that combines all the demand for a period into one order for the item.</span></span> <span data-ttu-id="d52ea-136">Ordern planeras under den första dagen i perioden och dess kvantitet uppfyller nettokraven under den fastställda perioden.</span><span class="sxs-lookup"><span data-stu-id="d52ea-136">The order will be planned for the first day of the period and its quantity will fulfill the net requirements during the established period.</span></span> <span data-ttu-id="d52ea-137">Perioden inleds med det första efter frågan av artikeln och täcker den definierade tiden i tid.</span><span class="sxs-lookup"><span data-stu-id="d52ea-137">The period starts with the first demand of the item and covers the defined length in time.</span></span> <span data-ttu-id="d52ea-138">Nästa period kommer att inledas med nästa behov av artikeln.</span><span class="sxs-lookup"><span data-stu-id="d52ea-138">The next period will start with the next requirements of the item.</span></span>
- <span data-ttu-id="d52ea-139">**Minsta/högsta** - den partistorleksmetod som innehåller påfyllningen av lagret upp till en viss nivå när den förutsagda behållningen är under ett tröskelvärde.</span><span class="sxs-lookup"><span data-stu-id="d52ea-139">**Min/Max** - The lot-sizing method that contains the replenishment of inventory up to a certain level when the predicted on-hand is below a threshold.</span></span> <span data-ttu-id="d52ea-140">Kvantiteten för påfyllnaden är differensen mellan den högsta nivån och den förutsagda behållningsnivån.</span><span class="sxs-lookup"><span data-stu-id="d52ea-140">The replenishment quantity will be the difference between the maximum level and the predicted on-hand level.</span></span>


## <a name="additional-resources"></a><span data-ttu-id="d52ea-141">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="d52ea-141">Additional resources</span></span>

[<span data-ttu-id="d52ea-142">Huvudplaner</span><span class="sxs-lookup"><span data-stu-id="d52ea-142">Master plans</span></span>](master-plans.md)
