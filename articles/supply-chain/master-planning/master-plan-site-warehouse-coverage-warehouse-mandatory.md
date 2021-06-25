---
title: Huvudplanering för täckning av site och lagerställe, lagerställe obligatorisk
description: Det här avsnittet beskriver hur en artikel som har plats och lagerställe som disponeringsdimensioner planeras. Lagerdimensionen är obligatorisk.
author: roxanadiaconu
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResStorageDimensionGroup, ReqItemTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2554
ms.assetid: 3211e95f-b91a-4d27-8d92-f328ae2bcf12
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 132a7171488b3c4da8ef13e11bed87c78071744d
ms.sourcegitcommit: ff09736563d3cd2bc74c7664edd1767b218401cb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "6187468"
---
# <a name="master-planning-for-site-and-warehouse-coverage-warehouse-mandatory"></a><span data-ttu-id="98211-104">Huvudplanering för täckning av site och lagerställe, lagerställe obligatorisk</span><span class="sxs-lookup"><span data-stu-id="98211-104">Master planning for site and warehouse coverage, warehouse mandatory</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="98211-105">Det här avsnittet beskriver hur en artikel som har plats och lagerställe som disponeringsdimensioner planeras.</span><span class="sxs-lookup"><span data-stu-id="98211-105">This topic describes how an item that has site and warehouse as coverage dimensions is planned.</span></span> <span data-ttu-id="98211-106">Lagerdimensionen är obligatorisk.</span><span class="sxs-lookup"><span data-stu-id="98211-106">The warehouse dimension is mandatory.</span></span>

<span data-ttu-id="98211-107">Det här huvudplaneringsscenariot omfattar följande villkor:</span><span class="sxs-lookup"><span data-stu-id="98211-107">This master planning scenario involves the following conditions:</span></span>

-   <span data-ttu-id="98211-108">Dimensionen på en site är obligatorisk och måste anges på efterfrågetransaktionen.</span><span class="sxs-lookup"><span data-stu-id="98211-108">The site dimension is set to mandatory and must be entered on the demand transaction.</span></span>
-   <span data-ttu-id="98211-109">Lagerställedimensionen är obligatorisk och måste anges på efterfrågetransaktionen.</span><span class="sxs-lookup"><span data-stu-id="98211-109">The warehouse dimension is set to mandatory and must be entered on the demand transaction.</span></span>
-   <span data-ttu-id="98211-110">Site- och lagerställedimensionerna är inställda för disponeringsplanering.</span><span class="sxs-lookup"><span data-stu-id="98211-110">The site and warehouse dimensions are set for coverage planning.</span></span> <span data-ttu-id="98211-111">Andra dimensioner kan också ha valts för disponeringsplanering.</span><span class="sxs-lookup"><span data-stu-id="98211-111">Other dimensions may be set for coverage planning also.</span></span> <span data-ttu-id="98211-112">De påverkas emellertid inte av multisitefunktionen.</span><span class="sxs-lookup"><span data-stu-id="98211-112">However, they are not affected by the multisite functionality.</span></span>

<span data-ttu-id="98211-113">Följande figur illustrerar hur huvudplaneringen fortskrider.</span><span class="sxs-lookup"><span data-stu-id="98211-113">The following graphic illustrates how master planning proceeds.</span></span> <span data-ttu-id="98211-114">Parametrarna som refereras i bilden och deras siter är som följer:</span><span class="sxs-lookup"><span data-stu-id="98211-114">The parameters that are referred to in the graphic, and their locations, are as follows:</span></span>
-   <span data-ttu-id="98211-115">Lagret har inställningen **Manuellt**.</span><span class="sxs-lookup"><span data-stu-id="98211-115">The warehouse is set to **Manual**.</span></span> <span data-ttu-id="98211-116">Klick på **Lagerhantering &gt; Inställningar &gt; Lagerindelning &gt; Lagerställen**.</span><span class="sxs-lookup"><span data-stu-id="98211-116">Click **Inventory management &gt; Setup &gt; Inventory breakdown &gt; Warehouses**.</span></span> <span data-ttu-id="98211-117">Se fältet **Manuell** på snabbfliken **Huvudplanering**.</span><span class="sxs-lookup"><span data-stu-id="98211-117">On the **Master planning** FastTab, see the **Manual** field.</span></span>
-   <span data-ttu-id="98211-118">Disponeringsplanering har definierats för artikeln.</span><span class="sxs-lookup"><span data-stu-id="98211-118">Item coverage is defined for the item.</span></span> <span data-ttu-id="98211-119">Klicka på **Hantering av produktinformation &gt; Produkter&gt; Frisläppta produkter**.</span><span class="sxs-lookup"><span data-stu-id="98211-119">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="98211-120">Markera artikeln innan du i åtgärdsfönstret, på fliken **Plan**, klickar på **Artikeldisponering**.</span><span class="sxs-lookup"><span data-stu-id="98211-120">Select the item, and then, on the Action Pane, on the **Plan** tab, click **Item coverage**.</span></span>
-   <span data-ttu-id="98211-121">Påfyllningsrelationer har definierats för lagret.</span><span class="sxs-lookup"><span data-stu-id="98211-121">Refill relations are defined for the warehouse.</span></span> <span data-ttu-id="98211-122">Klick på **Lagerhantering &gt; Inställningar &gt; Lagerindelning &gt; Lagerställen**.</span><span class="sxs-lookup"><span data-stu-id="98211-122">Click **Inventory management &gt; Setup &gt; Inventory breakdown &gt; Warehouses**.</span></span> <span data-ttu-id="98211-123">Gå till snabbfliken **Huvudplanering** och leta reda på fältgruppen **Huvudlagerställe**.</span><span class="sxs-lookup"><span data-stu-id="98211-123">On the **Master planning** FastTab, see the **Main warehouse** field group.</span></span>
-   <span data-ttu-id="98211-124">Standardordertypen anges som Produktion, Inköpsorder eller Kanban.</span><span class="sxs-lookup"><span data-stu-id="98211-124">The default order type is set to Production, Purchase order, or Kanban.</span></span> <span data-ttu-id="98211-125">Klicka på **Hantering av produktinformation &gt; Produkter&gt; Frisläppta produkter**.</span><span class="sxs-lookup"><span data-stu-id="98211-125">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="98211-126">Markera artikeln innan du i åtgärdsfönstret, på fliken **Plan**, klickar på **Standardorderinställningar**.</span><span class="sxs-lookup"><span data-stu-id="98211-126">Select the item, and then, on the Action Pane, on the **Plan** tab, click **Default order settings**.</span></span> <span data-ttu-id="98211-127">Se **Standardordertyp** i formuläret **Standardorderinställningar**.</span><span class="sxs-lookup"><span data-stu-id="98211-127">In the **Default order settings** form, see the **Default order type**.</span></span>

![Efterfrågenedbrytning för täckning av site och lagerställe, lagerställe obligatoriskt](./media/multisitedemandexplosionscenarioforsiteandwarehousecoveragewarehousemandatory.jpg)



## <a name="additional-resources"></a><span data-ttu-id="98211-129">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="98211-129">Additional resources</span></span>

[<span data-ttu-id="98211-130">Huvudplanering och multisitefunktioner – översikt</span><span class="sxs-lookup"><span data-stu-id="98211-130">Master planning and multisite functionality overview</span></span>](master-plan-multisite-functionality.md)

[<span data-ttu-id="98211-131">Huvudplanering för täckning av plats, lagerställe obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="98211-131">Master planning for site coverage, mandatory warehouse</span></span>](master-plan-site-coverage-warehouse-mandatory.md)

[<span data-ttu-id="98211-132">Huvudplanering för täckning av plats, lagerställe inte obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="98211-132">Master planning for site coverage, warehouse not mandatory</span></span>](master-plan-site-coverage-warehouse-not-mandatory.md)

[<span data-ttu-id="98211-133">Huvudplanering för plats och lagerställe, lagerställe inte obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="98211-133">Master planning for site and warehouse coverage, warehouse not mandatory</span></span>](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[<span data-ttu-id="98211-134">Avgör strukturlisteversion</span><span class="sxs-lookup"><span data-stu-id="98211-134">Determine the BOM version</span></span>](master-plan-bom-version-determined.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]