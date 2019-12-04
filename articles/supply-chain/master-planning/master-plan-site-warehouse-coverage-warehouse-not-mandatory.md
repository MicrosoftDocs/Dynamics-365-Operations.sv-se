---
title: Huvudplanering för täckning av site och lagerställe, lagerställe inte obligatorisk
description: Det här avsnittet beskriver hur en artikel som har plats och lagerställe som disponeringsdimensioner planeras. Lagerdimensionen är inte obligatorisk.
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResStorageDimensionGroup, ReqItemTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2514
ms.assetid: 92d47bdd-df68-4f60-ac9a-96aa08236c26
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cea228e04632bd61f60771b09481241df5d16bd3
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/18/2019
ms.locfileid: "2813717"
---
# <a name="master-planning-for-site-and-warehouse-coverage-warehouse-not-mandatory"></a><span data-ttu-id="64837-104">Huvudplanering för täckning av site och lagerställe, lagerställe inte obligatorisk</span><span class="sxs-lookup"><span data-stu-id="64837-104">Master planning for site and warehouse coverage, warehouse not mandatory</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="64837-105">Det här avsnittet beskriver hur en artikel som har plats och lagerställe som disponeringsdimensioner planeras.</span><span class="sxs-lookup"><span data-stu-id="64837-105">This topic describes how an item that has site and warehouse as coverage dimensions is planned.</span></span> <span data-ttu-id="64837-106">Lagerdimensionen är inte obligatorisk.</span><span class="sxs-lookup"><span data-stu-id="64837-106">The warehouse dimension is not mandatory.</span></span>

<span data-ttu-id="64837-107">Det här huvudplaneringsscenariot omfattar följande villkor:</span><span class="sxs-lookup"><span data-stu-id="64837-107">This master planning scenario involves the following conditions:</span></span>

-   <span data-ttu-id="64837-108">Dimensionen på en site är obligatorisk och måste anges på efterfrågetransaktionen.</span><span class="sxs-lookup"><span data-stu-id="64837-108">The site dimension is set to mandatory and must be entered on the demand transaction.</span></span> <span data-ttu-id="64837-109">Den här inställningen går inte att ändra.</span><span class="sxs-lookup"><span data-stu-id="64837-109">This setting can't be modified.</span></span>
-   <span data-ttu-id="64837-110">Lagerdimensionen har inte angetts vara obligatorisk.</span><span class="sxs-lookup"><span data-stu-id="64837-110">The warehouse dimension is not set to mandatory.</span></span> <span data-ttu-id="64837-111">Lagret kan vara känt, men det används inte vid beräkningen av huvudplaneringen.</span><span class="sxs-lookup"><span data-stu-id="64837-111">The warehouse may be known, but it is not used in the master planning calculation.</span></span>
-   <span data-ttu-id="64837-112">Plats- och lagerdimensionerna är inställda på disponeringsplanering.</span><span class="sxs-lookup"><span data-stu-id="64837-112">The site and warehouse dimensions are set for coverage planning.</span></span> <span data-ttu-id="64837-113">Andra dimensioner kan också ha valts för disponeringsplanering.</span><span class="sxs-lookup"><span data-stu-id="64837-113">Other dimensions may be set for coverage planning also.</span></span> <span data-ttu-id="64837-114">De påverkas emellertid inte av multisitefunktionen.</span><span class="sxs-lookup"><span data-stu-id="64837-114">However, they are not affected by the multisite functionality.</span></span>

<span data-ttu-id="64837-115">Följande figur illustrerar hur huvudplaneringen fortskrider.</span><span class="sxs-lookup"><span data-stu-id="64837-115">The following graphic illustrates how master planning proceeds.</span></span> <span data-ttu-id="64837-116">Parametrarna som refereras i bilden och deras siter är som följer:</span><span class="sxs-lookup"><span data-stu-id="64837-116">The parameters that are referred to in the graphic, and their locations, are as follows:</span></span>
-   <span data-ttu-id="64837-117">Lagret har inställningen Manuellt.</span><span class="sxs-lookup"><span data-stu-id="64837-117">The warehouse is set to Manual.</span></span> <span data-ttu-id="64837-118">Klick på **Lagerhantering &gt; Inställningar &gt; Lagerindelning &gt; Lagerställen**.</span><span class="sxs-lookup"><span data-stu-id="64837-118">Click **Inventory management &gt; Setup &gt; Inventory breakdown &gt; Warehouses**.</span></span> <span data-ttu-id="64837-119">Se fältet **Manuell** på snabbfliken **Huvudplanering**.</span><span class="sxs-lookup"><span data-stu-id="64837-119">On the **Master planning** FastTab, see the **Manual** field.</span></span>
-   <span data-ttu-id="64837-120">Disponeringsplanering har definierats för artikeln.</span><span class="sxs-lookup"><span data-stu-id="64837-120">Item coverage is defined for the item.</span></span> <span data-ttu-id="64837-121">Klicka på **Hantering av produktinformation &gt; Produkter&gt; Frisläppta produkter**.</span><span class="sxs-lookup"><span data-stu-id="64837-121">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="64837-122">Markera artikeln och sedan, i åtgärdsfönstret, på fliken **Plan**, klickar du på **Artikeldisponering**.</span><span class="sxs-lookup"><span data-stu-id="64837-122">Select the item, and then, on the Action pane, on the **Plan** tab, click **Item coverage**.</span></span>
-   <span data-ttu-id="64837-123">Påfyllningsrelationer har definierats för lagret.</span><span class="sxs-lookup"><span data-stu-id="64837-123">Refill relations are defined for the warehouse.</span></span> <span data-ttu-id="64837-124">Klick på **Lagerhantering &gt; Inställningar &gt; Lagerindelning &gt; Lagerställen**.</span><span class="sxs-lookup"><span data-stu-id="64837-124">Click **Inventory management &gt; Setup &gt; Inventory breakdown &gt; Warehouses**.</span></span> <span data-ttu-id="64837-125">Gå till snabbfliken **Huvudplanering** och leta reda på fältgruppen **Huvudlagerställe**.</span><span class="sxs-lookup"><span data-stu-id="64837-125">On the **Master planning** FastTab, see the **Main warehouse** field group.</span></span>
-   <span data-ttu-id="64837-126">Standardordertypen anges som Produktion, Inköpsorder eller Kanban.</span><span class="sxs-lookup"><span data-stu-id="64837-126">The default order type is set to Production, Purchase order, or Kanban.</span></span> <span data-ttu-id="64837-127">Klicka på **Hantering av produktinformation &gt; Produkter&gt; Frisläppta produkter**.</span><span class="sxs-lookup"><span data-stu-id="64837-127">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="64837-128">Markera artikeln och sedan, i åtgärdsfönstret, på fliken **Plan**, klickar du på **Standardorderinställningar**.</span><span class="sxs-lookup"><span data-stu-id="64837-128">Select the item, and then, on the Action pane, on the **Plan** tab, click **Default order settings**.</span></span> <span data-ttu-id="64837-129">Se **Standardordertyp** i formuläret **Standardorderinställningar**.</span><span class="sxs-lookup"><span data-stu-id="64837-129">In the **Default order settings** form, see the **Default order type**.</span></span>

![Efterfrågenedbrytning för site och lagerställe, lagerställe ej obligatoriskt](./media/multisitedemandexplosionscenarioforsiteandwarehousecoveragewarehousenotmandatory.jpg)



<a name="additional-resources"></a><span data-ttu-id="64837-131">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="64837-131">Additional resources</span></span>
--------

[<span data-ttu-id="64837-132">Huvudplanering och multisitefunktioner – översikt</span><span class="sxs-lookup"><span data-stu-id="64837-132">Master planning and multisite functionality overview</span></span>](master-plan-multisite-functionality.md)

[<span data-ttu-id="64837-133">Huvudplanering för täckning av plats, lagerställe obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="64837-133">Master planning for site coverage, mandatory warehouse</span></span>](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[<span data-ttu-id="64837-134">Huvudplanering för plats och lagerställe, lagerställe obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="64837-134">Master planning for site and warehouse coverage, warehouse mandatory</span></span>](master-plan-site-coverage-warehouse-mandatory.md)

[<span data-ttu-id="64837-135">Huvudplanering för plats och lagerställe, lagerställe inte obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="64837-135">Master planning for site and warehouse coverage, warehouse not mandatory</span></span>](master-plan-site-coverage-warehouse-not-mandatory.md)

[<span data-ttu-id="64837-136">Avgör strukturlisteversion</span><span class="sxs-lookup"><span data-stu-id="64837-136">Determine the BOM version</span></span>](master-plan-bom-version-determined.md)



