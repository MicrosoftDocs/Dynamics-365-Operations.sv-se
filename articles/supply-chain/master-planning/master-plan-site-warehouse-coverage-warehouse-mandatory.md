---
title: Huvudplanering för täckning av site och lagerställe, lagerställe obligatorisk
description: Det här avsnittet beskriver hur en artikel som har plats och lagerställe som disponeringsdimensioner planeras. Lagerdimensionen är obligatorisk.
author: roxanadiaconu
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResStorageDimensionGroup, ReqItemTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2554
ms.assetid: 3211e95f-b91a-4d27-8d92-f328ae2bcf12
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a07a4588d042af53d6281afc174ff58ecf24ca06
ms.sourcegitcommit: 8a2127c5af6cdbda30ccc1f9bef9bd4ab61e9e50
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/18/2020
ms.locfileid: "3383353"
---
# <a name="master-planning-for-site-and-warehouse-coverage-warehouse-mandatory"></a><span data-ttu-id="6ab45-104">Huvudplanering för täckning av site och lagerställe, lagerställe obligatorisk</span><span class="sxs-lookup"><span data-stu-id="6ab45-104">Master planning for site and warehouse coverage, warehouse mandatory</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6ab45-105">Det här avsnittet beskriver hur en artikel som har plats och lagerställe som disponeringsdimensioner planeras.</span><span class="sxs-lookup"><span data-stu-id="6ab45-105">This topic describes how an item that has site and warehouse as coverage dimensions is planned.</span></span> <span data-ttu-id="6ab45-106">Lagerdimensionen är obligatorisk.</span><span class="sxs-lookup"><span data-stu-id="6ab45-106">The warehouse dimension is mandatory.</span></span>

<span data-ttu-id="6ab45-107">Det här huvudplaneringsscenariot omfattar följande villkor:</span><span class="sxs-lookup"><span data-stu-id="6ab45-107">This master planning scenario involves the following conditions:</span></span>

-   <span data-ttu-id="6ab45-108">Dimensionen på en site är obligatorisk och måste anges på efterfrågetransaktionen.</span><span class="sxs-lookup"><span data-stu-id="6ab45-108">The site dimension is set to mandatory and must be entered on the demand transaction.</span></span>
-   <span data-ttu-id="6ab45-109">Lagerställedimensionen är obligatorisk och måste anges på efterfrågetransaktionen.</span><span class="sxs-lookup"><span data-stu-id="6ab45-109">The warehouse dimension is set to mandatory and must be entered on the demand transaction.</span></span>
-   <span data-ttu-id="6ab45-110">Site- och lagerställedimensionerna är inställda för disponeringsplanering.</span><span class="sxs-lookup"><span data-stu-id="6ab45-110">The site and warehouse dimensions are set for coverage planning.</span></span> <span data-ttu-id="6ab45-111">Andra dimensioner kan också ha valts för disponeringsplanering.</span><span class="sxs-lookup"><span data-stu-id="6ab45-111">Other dimensions may be set for coverage planning also.</span></span> <span data-ttu-id="6ab45-112">De påverkas emellertid inte av multisitefunktionen.</span><span class="sxs-lookup"><span data-stu-id="6ab45-112">However, they are not affected by the multisite functionality.</span></span>

<span data-ttu-id="6ab45-113">Följande figur illustrerar hur huvudplaneringen fortskrider.</span><span class="sxs-lookup"><span data-stu-id="6ab45-113">The following graphic illustrates how master planning proceeds.</span></span> <span data-ttu-id="6ab45-114">Parametrarna som refereras i bilden och deras siter är som följer:</span><span class="sxs-lookup"><span data-stu-id="6ab45-114">The parameters that are referred to in the graphic, and their locations, are as follows:</span></span>
-   <span data-ttu-id="6ab45-115">Lagret har inställningen **Manuellt**.</span><span class="sxs-lookup"><span data-stu-id="6ab45-115">The warehouse is set to **Manual**.</span></span> <span data-ttu-id="6ab45-116">Klick på **Lagerhantering &gt; Inställningar &gt; Lagerindelning &gt; Lagerställen**.</span><span class="sxs-lookup"><span data-stu-id="6ab45-116">Click **Inventory management &gt; Setup &gt; Inventory breakdown &gt; Warehouses**.</span></span> <span data-ttu-id="6ab45-117">Se fältet **Manuell** på snabbfliken **Huvudplanering**.</span><span class="sxs-lookup"><span data-stu-id="6ab45-117">On the **Master planning** FastTab, see the **Manual** field.</span></span>
-   <span data-ttu-id="6ab45-118">Disponeringsplanering har definierats för artikeln.</span><span class="sxs-lookup"><span data-stu-id="6ab45-118">Item coverage is defined for the item.</span></span> <span data-ttu-id="6ab45-119">Klicka på **Hantering av produktinformation &gt; Produkter&gt; Frisläppta produkter**.</span><span class="sxs-lookup"><span data-stu-id="6ab45-119">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="6ab45-120">Markera artikeln innan du i åtgärdsfönstret, på fliken **Plan**, klickar på **Artikeldisponering**.</span><span class="sxs-lookup"><span data-stu-id="6ab45-120">Select the item, and then, on the Action Pane, on the **Plan** tab, click **Item coverage**.</span></span>
-   <span data-ttu-id="6ab45-121">Påfyllningsrelationer har definierats för lagret.</span><span class="sxs-lookup"><span data-stu-id="6ab45-121">Refill relations are defined for the warehouse.</span></span> <span data-ttu-id="6ab45-122">Klick på **Lagerhantering &gt; Inställningar &gt; Lagerindelning &gt; Lagerställen**.</span><span class="sxs-lookup"><span data-stu-id="6ab45-122">Click **Inventory management &gt; Setup &gt; Inventory breakdown &gt; Warehouses**.</span></span> <span data-ttu-id="6ab45-123">Gå till snabbfliken **Huvudplanering** och leta reda på fältgruppen **Huvudlagerställe**.</span><span class="sxs-lookup"><span data-stu-id="6ab45-123">On the **Master planning** FastTab, see the **Main warehouse** field group.</span></span>
-   <span data-ttu-id="6ab45-124">Standardordertypen anges som Produktion, Inköpsorder eller Kanban.</span><span class="sxs-lookup"><span data-stu-id="6ab45-124">The default order type is set to Production, Purchase order, or Kanban.</span></span> <span data-ttu-id="6ab45-125">Klicka på **Hantering av produktinformation &gt; Produkter&gt; Frisläppta produkter**.</span><span class="sxs-lookup"><span data-stu-id="6ab45-125">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="6ab45-126">Markera artikeln innan du i åtgärdsfönstret, på fliken **Plan**, klickar på **Standardorderinställningar**.</span><span class="sxs-lookup"><span data-stu-id="6ab45-126">Select the item, and then, on the Action Pane, on the **Plan** tab, click **Default order settings**.</span></span> <span data-ttu-id="6ab45-127">Se **Standardordertyp** i formuläret **Standardorderinställningar**.</span><span class="sxs-lookup"><span data-stu-id="6ab45-127">In the **Default order settings** form, see the **Default order type**.</span></span>

![Efterfrågenedbrytning för täckning av site och lagerställe, lagerställe obligatoriskt](./media/multisitedemandexplosionscenarioforsiteandwarehousecoveragewarehousemandatory.jpg)



<a name="additional-resources"></a><span data-ttu-id="6ab45-129">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="6ab45-129">Additional resources</span></span>
--------

[<span data-ttu-id="6ab45-130">Huvudplanering och multisitefunktioner – översikt</span><span class="sxs-lookup"><span data-stu-id="6ab45-130">Master planning and multisite functionality overview</span></span>](master-plan-multisite-functionality.md)

[<span data-ttu-id="6ab45-131">Huvudplanering för täckning av plats, lagerställe obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="6ab45-131">Master planning for site coverage, mandatory warehouse</span></span>](master-plan-site-coverage-warehouse-mandatory.md)

[<span data-ttu-id="6ab45-132">Huvudplanering för täckning av plats, lagerställe inte obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="6ab45-132">Master planning for site coverage, warehouse not mandatory</span></span>](master-plan-site-coverage-warehouse-not-mandatory.md)

[<span data-ttu-id="6ab45-133">Huvudplanering för plats och lagerställe, lagerställe inte obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="6ab45-133">Master planning for site and warehouse coverage, warehouse not mandatory</span></span>](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[<span data-ttu-id="6ab45-134">Avgör strukturlisteversion</span><span class="sxs-lookup"><span data-stu-id="6ab45-134">Determine the BOM version</span></span>](master-plan-bom-version-determined.md)



