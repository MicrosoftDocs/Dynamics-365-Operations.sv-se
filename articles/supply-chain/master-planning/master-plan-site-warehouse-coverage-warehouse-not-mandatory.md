---
title: "Huvudplanering för täckning av site och lagerställe, lagerställe inte obligatorisk"
description: "Det här avsnittet beskriver hur en artikel som har plats och lagerställe som disponeringsdimensioner planeras. Lagerdimensionen är inte obligatorisk."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResStorageDimensionGroup, ReqItemTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 2514
ms.assetid: 92d47bdd-df68-4f60-ac9a-96aa08236c26
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: b9214a8f2b62aa261b05f0b360fd03faa63ce1ea
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="master-planning-for-site-and-warehouse-coverage-warehouse-not-mandatory"></a><span data-ttu-id="2a496-104">Huvudplanering för täckning av site och lagerställe, lagerställe inte obligatorisk</span><span class="sxs-lookup"><span data-stu-id="2a496-104">Master planning for site and warehouse coverage, warehouse not mandatory</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="2a496-105">Det här avsnittet beskriver hur en artikel som har plats och lagerställe som disponeringsdimensioner planeras.</span><span class="sxs-lookup"><span data-stu-id="2a496-105">This topic describes how an item that has site and warehouse as coverage dimensions is planned.</span></span> <span data-ttu-id="2a496-106">Lagerdimensionen är inte obligatorisk.</span><span class="sxs-lookup"><span data-stu-id="2a496-106">The warehouse dimension is not mandatory.</span></span>

<span data-ttu-id="2a496-107">Det här huvudplaneringsscenariot omfattar följande villkor:</span><span class="sxs-lookup"><span data-stu-id="2a496-107">This master planning scenario involves the following conditions:</span></span>

-   <span data-ttu-id="2a496-108">Dimensionen på en site är obligatorisk och måste anges på efterfrågetransaktionen.</span><span class="sxs-lookup"><span data-stu-id="2a496-108">The site dimension is set to mandatory and must be entered on the demand transaction.</span></span> <span data-ttu-id="2a496-109">Den här inställningen går inte att ändra.</span><span class="sxs-lookup"><span data-stu-id="2a496-109">This setting can't be modified.</span></span>
-   <span data-ttu-id="2a496-110">Lagerdimensionen har inte angetts vara obligatorisk.</span><span class="sxs-lookup"><span data-stu-id="2a496-110">The warehouse dimension is not set to mandatory.</span></span> <span data-ttu-id="2a496-111">Lagret kan vara känt, men det används inte vid beräkningen av huvudplaneringen.</span><span class="sxs-lookup"><span data-stu-id="2a496-111">The warehouse may be known, but it is not used in the master planning calculation.</span></span>
-   <span data-ttu-id="2a496-112">Plats- och lagerdimensionerna är inställda på disponeringsplanering.</span><span class="sxs-lookup"><span data-stu-id="2a496-112">The site and warehouse dimensions are set for coverage planning.</span></span> <span data-ttu-id="2a496-113">Andra dimensioner kan också ha valts för disponeringsplanering.</span><span class="sxs-lookup"><span data-stu-id="2a496-113">Other dimensions may be set for coverage planning also.</span></span> <span data-ttu-id="2a496-114">De påverkas emellertid inte av multisitefunktionen.</span><span class="sxs-lookup"><span data-stu-id="2a496-114">However, they are not affected by the multisite functionality.</span></span>

<span data-ttu-id="2a496-115">Följande figur illustrerar hur huvudplaneringen fortskrider.</span><span class="sxs-lookup"><span data-stu-id="2a496-115">The following graphic illustrates how master planning proceeds.</span></span> <span data-ttu-id="2a496-116">Parametrarna som refereras i bilden och deras siter är som följer:</span><span class="sxs-lookup"><span data-stu-id="2a496-116">The parameters that are referred to in the graphic, and their locations, are as follows:</span></span>
-   <span data-ttu-id="2a496-117">Lagret har inställningen Manuellt.</span><span class="sxs-lookup"><span data-stu-id="2a496-117">The warehouse is set to Manual.</span></span> <span data-ttu-id="2a496-118">Klick på **Lagerhantering &gt; Inställningar &gt; Lagerindelning &gt; Lagerställen**.</span><span class="sxs-lookup"><span data-stu-id="2a496-118">Click **Inventory management &gt; Setup &gt; Inventory breakdown &gt; Warehouses**.</span></span> <span data-ttu-id="2a496-119">Se fältet **Manuell** på snabbfliken **Huvudplanering**.</span><span class="sxs-lookup"><span data-stu-id="2a496-119">On the **Master planning** FastTab, see the **Manual** field.</span></span>
-   <span data-ttu-id="2a496-120">Disponeringsplanering har definierats för artikeln.</span><span class="sxs-lookup"><span data-stu-id="2a496-120">Item coverage is defined for the item.</span></span> <span data-ttu-id="2a496-121">Klicka på **Hantering av produktinformation &gt; Produkter&gt; Frisläppta produkter**.</span><span class="sxs-lookup"><span data-stu-id="2a496-121">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="2a496-122">Markera artikeln och sedan, i åtgärdsfönstret, på fliken **Plan**, klickar du på **Artikeldisponering**.</span><span class="sxs-lookup"><span data-stu-id="2a496-122">Select the item, and then, on the Action pane, on the **Plan** tab, click **Item coverage**.</span></span>
-   <span data-ttu-id="2a496-123">Påfyllningsrelationer har definierats för lagret.</span><span class="sxs-lookup"><span data-stu-id="2a496-123">Refill relations are defined for the warehouse.</span></span> <span data-ttu-id="2a496-124">Klick på **Lagerhantering &gt; Inställningar &gt; Lagerindelning &gt; Lagerställen**.</span><span class="sxs-lookup"><span data-stu-id="2a496-124">Click **Inventory management &gt; Setup &gt; Inventory breakdown &gt; Warehouses**.</span></span> <span data-ttu-id="2a496-125">Gå till snabbfliken **Huvudplanering** och leta reda på fältgruppen **Huvudlagerställe**.</span><span class="sxs-lookup"><span data-stu-id="2a496-125">On the **Master planning** FastTab, see the **Main warehouse** field group.</span></span>
-   <span data-ttu-id="2a496-126">Standardordertypen anges som Produktion, Inköpsorder eller Kanban.</span><span class="sxs-lookup"><span data-stu-id="2a496-126">The default order type is set to Production, Purchase order, or Kanban.</span></span> <span data-ttu-id="2a496-127">Klicka på **Hantering av produktinformation &gt; Produkter&gt; Frisläppta produkter**.</span><span class="sxs-lookup"><span data-stu-id="2a496-127">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="2a496-128">Markera artikeln och sedan, i åtgärdsfönstret, på fliken **Plan**, klickar du på **Standardorderinställningar**.</span><span class="sxs-lookup"><span data-stu-id="2a496-128">Select the item, and then, on the Action pane, on the **Plan** tab, click **Default order settings**.</span></span> <span data-ttu-id="2a496-129">Se **Standardordertyp** i formuläret **Standardorderinställningar**.</span><span class="sxs-lookup"><span data-stu-id="2a496-129">In the **Default order settings** form, see the **Default order type**.</span></span>

![Efterfrågenedbrytning för site och lagerställe, lagerställe ej obligatoriskt](./media/multisitedemandexplosionscenarioforsiteandwarehousecoveragewarehousenotmandatory.jpg)

 
-



<a name="see-also"></a><span data-ttu-id="2a496-131">Se även</span><span class="sxs-lookup"><span data-stu-id="2a496-131">See also</span></span>
--------

[<span data-ttu-id="2a496-132">Huvudplanering och multiplatsfunktioner</span><span class="sxs-lookup"><span data-stu-id="2a496-132">Master planning and multisite functionality</span></span>](master-plan-multisite-functionality.md)

[<span data-ttu-id="2a496-133">Huvudplanering - täckning av site och lagerställe, lagerställe obligatorisk</span><span class="sxs-lookup"><span data-stu-id="2a496-133">Master planning - site and warehouse coverage, warehouse mandatory</span></span>](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[<span data-ttu-id="2a496-134">Huvudplanering - platstäckning, lagerställe obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="2a496-134">Master planning - site coverage, warehouse mandatory</span></span>](master-plan-site-coverage-warehouse-mandatory.md)

[<span data-ttu-id="2a496-135">Huvudplanering - täckning av site, lagerställe ej obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="2a496-135">Master planning - site coverage, warehouse not mandatory</span></span>](master-plan-site-coverage-warehouse-not-mandatory.md)

[<span data-ttu-id="2a496-136">Huvudplanering - hur strukturlisteversionen bestäms</span><span class="sxs-lookup"><span data-stu-id="2a496-136">Master planning - How the BOM version is determined</span></span>](master-plan-bom-version-determined.md)




