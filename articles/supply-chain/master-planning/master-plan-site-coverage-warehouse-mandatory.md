---
title: Huvudplanering för täckning av plats, obligatoriskt lagerställe
description: Det här avsnittet innehåller en beskrivning av hur en artikel som har webbplatsen som disponeringsdimension planeras. Lagerställe är en obligatorisk dimension.
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
ms.custom: 2454
ms.assetid: aa135030-f98c-48bf-902c-e52f680dc247
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5a6128900d403c05af611b7636d5768b1c6a0b2f
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "3213709"
---
# <a name="master-planning-for-site-coverage-mandatory-warehouse"></a><span data-ttu-id="b49a4-104">Huvudplanering för täckning av plats, obligatoriskt lagerställe</span><span class="sxs-lookup"><span data-stu-id="b49a4-104">Master planning for site coverage, mandatory warehouse</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b49a4-105">Det här avsnittet innehåller en beskrivning av hur en artikel som har webbplatsen som disponeringsdimension planeras.</span><span class="sxs-lookup"><span data-stu-id="b49a4-105">This topic describes how an item that has the site as coverage dimension is planned.</span></span> <span data-ttu-id="b49a4-106">Lagerställe är en obligatorisk dimension.</span><span class="sxs-lookup"><span data-stu-id="b49a4-106">Warehouse is a mandatory dimension.</span></span>

<span data-ttu-id="b49a4-107">Det här huvudplaneringsscenariot omfattar följande villkor:</span><span class="sxs-lookup"><span data-stu-id="b49a4-107">This master planning scenario involves the following conditions:</span></span>

-   <span data-ttu-id="b49a4-108">Dimensionen på en site är obligatorisk och måste anges på efterfrågetransaktionen.</span><span class="sxs-lookup"><span data-stu-id="b49a4-108">The site dimension is set to mandatory and must be entered on the demand transaction.</span></span> <span data-ttu-id="b49a4-109">Den här inställningen går inte att ändra.</span><span class="sxs-lookup"><span data-stu-id="b49a4-109">This setting can't be modified.</span></span>
-   <span data-ttu-id="b49a4-110">Lagerställedimensionen är obligatorisk och måste anges på efterfrågetransaktionen.</span><span class="sxs-lookup"><span data-stu-id="b49a4-110">The warehouse dimension is set to mandatory and must be entered on the demand transaction.</span></span>
-   <span data-ttu-id="b49a4-111">Sitedimensionen är aktiverad för disponeringsplanering.</span><span class="sxs-lookup"><span data-stu-id="b49a4-111">The site dimension is set for coverage planning.</span></span> <span data-ttu-id="b49a4-112">Även andra dimensioner kan ställas in för disponeringsplanering.</span><span class="sxs-lookup"><span data-stu-id="b49a4-112">Other dimensions may be set for coverage planning also.</span></span> <span data-ttu-id="b49a4-113">De påverkas dock inte av multisitefunktionen.</span><span class="sxs-lookup"><span data-stu-id="b49a4-113">However, they are not affected by the multisite functionality.</span></span>
-   <span data-ttu-id="b49a4-114">Lagerställedimensionen är inte aktiverad för disponeringsplanering.</span><span class="sxs-lookup"><span data-stu-id="b49a4-114">The warehouse dimension is not set for coverage planning.</span></span> <span data-ttu-id="b49a4-115">Därför sammanställs tillgång och efterfrågan per site, och eventuellt, andra disponeringsplanerade dimensioner.</span><span class="sxs-lookup"><span data-stu-id="b49a4-115">Therefore, supply and demand are aggregated by site and, perhaps, other coverage-planned dimensions also.</span></span>

<span data-ttu-id="b49a4-116">Följande figur illustrerar hur huvudplaneringen fortskrider.</span><span class="sxs-lookup"><span data-stu-id="b49a4-116">The following graphic illustrates how master planning proceeds.</span></span> <span data-ttu-id="b49a4-117">Parametrarna som refereras i bilden och deras siter är som följer:</span><span class="sxs-lookup"><span data-stu-id="b49a4-117">The parameters that are referred to in the graphic, and their locations, are as follows:</span></span>
-   <span data-ttu-id="b49a4-118">Disponeringsplanering har definierats för artikeln.</span><span class="sxs-lookup"><span data-stu-id="b49a4-118">Item coverage is defined for the item.</span></span> <span data-ttu-id="b49a4-119">Klicka på **Hantering av produktinformation &gt; Produkter&gt; Frisläppta produkter**.</span><span class="sxs-lookup"><span data-stu-id="b49a4-119">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="b49a4-120">Markera artikeln och klicka sedan på **Plan &gt; Artikeldisponering**.</span><span class="sxs-lookup"><span data-stu-id="b49a4-120">Select the item, and then click **Plan &gt; Item coverage**.</span></span>
-   <span data-ttu-id="b49a4-121">Påfyllningsrelationer har definierats för lagret.</span><span class="sxs-lookup"><span data-stu-id="b49a4-121">Refill relations are defined for the warehouse.</span></span> <span data-ttu-id="b49a4-122">Klick på **Lagerhantering &gt; Inställningar &gt; Lagerindelning &gt; Lagerställen**.</span><span class="sxs-lookup"><span data-stu-id="b49a4-122">Click **Inventory management &gt; Setup &gt; Inventory breakdown &gt; Warehouses**.</span></span> <span data-ttu-id="b49a4-123">Gå till fliken **Huvudplanering** och leta reda på fältgruppen **Huvudlagerställe**.</span><span class="sxs-lookup"><span data-stu-id="b49a4-123">On the **Master planning** tab, see the **Main warehouse** field group.</span></span>
-   <span data-ttu-id="b49a4-124">Standardordertypen anges som Produktion, Inköpsorder eller Kanban.</span><span class="sxs-lookup"><span data-stu-id="b49a4-124">The default order type is set to Production, Purchase order, or Kanban.</span></span> <span data-ttu-id="b49a4-125">Klicka på **Hantering av produktinformation &gt; Produkter&gt; Frisläppta produkter**.</span><span class="sxs-lookup"><span data-stu-id="b49a4-125">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="b49a4-126">Välj artikeln och klicka sedan på **Plan &gt; Standardorderinställningar**.</span><span class="sxs-lookup"><span data-stu-id="b49a4-126">Select the item, and then click **Plan &gt; Default order settings**.</span></span> <span data-ttu-id="b49a4-127">Se **Standardordertyp** i formuläret **Standardorderinställningar**.</span><span class="sxs-lookup"><span data-stu-id="b49a4-127">In the **Default order settings** form, see the **Default order type**.</span></span>

![Efterfrågenedbrytning för täckning av site, lagerställe obligatoriskt](./media/multisitedemandexplosionscenarioforsitecoveragewarehousemandatory.jpg)



<a name="additional-resources"></a><span data-ttu-id="b49a4-129">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="b49a4-129">Additional resources</span></span>
--------

[<span data-ttu-id="b49a4-130">Huvudplanering och multisitefunktioner – översikt</span><span class="sxs-lookup"><span data-stu-id="b49a4-130">Master planning and multisite functionality overview</span></span>](master-plan-multisite-functionality.md)

[<span data-ttu-id="b49a4-131">Huvudplanering för plats och lagerställe, lagerställe obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="b49a4-131">Master planning for site and warehouse coverage, warehouse mandatory</span></span>](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[<span data-ttu-id="b49a4-132">Huvudplanering för täckning av plats, lagerställe obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="b49a4-132">Master planning for site coverage, mandatory warehouse</span></span>](master-plan-site-coverage-warehouse-mandatory.md)

[<span data-ttu-id="b49a4-133">Huvudplanering för plats och lagerställe, lagerställe inte obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="b49a4-133">Master planning for site and warehouse coverage, warehouse not mandatory</span></span>](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[<span data-ttu-id="b49a4-134">Avgör strukturlisteversion</span><span class="sxs-lookup"><span data-stu-id="b49a4-134">Determine the BOM version</span></span>](master-plan-bom-version-determined.md)



