---
title: Huvudplanering för täckning av site och lagerställe, lagerställe obligatorisk
description: Det här avsnittet beskriver hur en artikel som har plats och lagerställe som disponeringsdimensioner planeras. Lagerdimensionen är obligatorisk.
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
ms.custom: 2554
ms.assetid: 3211e95f-b91a-4d27-8d92-f328ae2bcf12
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c52fc9955afe2a7502d0e1f9e7cdfc5b89bbb31d
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "365349"
---
# <a name="master-planning-for-site-and-warehouse-coverage-warehouse-mandatory"></a><span data-ttu-id="8c0cf-104">Huvudplanering för täckning av site och lagerställe, lagerställe obligatorisk</span><span class="sxs-lookup"><span data-stu-id="8c0cf-104">Master planning for site and warehouse coverage, warehouse mandatory</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8c0cf-105">Det här avsnittet beskriver hur en artikel som har plats och lagerställe som disponeringsdimensioner planeras.</span><span class="sxs-lookup"><span data-stu-id="8c0cf-105">This topic describes how an item that has site and warehouse as coverage dimensions is planned.</span></span> <span data-ttu-id="8c0cf-106">Lagerdimensionen är obligatorisk.</span><span class="sxs-lookup"><span data-stu-id="8c0cf-106">The warehouse dimension is mandatory.</span></span>

<span data-ttu-id="8c0cf-107">Det här huvudplaneringsscenariot omfattar följande villkor:</span><span class="sxs-lookup"><span data-stu-id="8c0cf-107">This master planning scenario involves the following conditions:</span></span>

-   <span data-ttu-id="8c0cf-108">Dimensionen på en site är obligatorisk och måste anges på efterfrågetransaktionen.</span><span class="sxs-lookup"><span data-stu-id="8c0cf-108">The site dimension is set to mandatory and must be entered on the demand transaction.</span></span>
-   <span data-ttu-id="8c0cf-109">Lagerställedimensionen är obligatorisk och måste anges på efterfrågetransaktionen.</span><span class="sxs-lookup"><span data-stu-id="8c0cf-109">The warehouse dimension is set to mandatory and must be entered on the demand transaction.</span></span>
-   <span data-ttu-id="8c0cf-110">Site- och lagerställedimensionerna är inställda för disponeringsplanering.</span><span class="sxs-lookup"><span data-stu-id="8c0cf-110">The site and warehouse dimensions are set for coverage planning.</span></span> <span data-ttu-id="8c0cf-111">Andra dimensioner kan också ha valts för disponeringsplanering.</span><span class="sxs-lookup"><span data-stu-id="8c0cf-111">Other dimensions may be set for coverage planning also.</span></span> <span data-ttu-id="8c0cf-112">De påverkas emellertid inte av multisitefunktionen.</span><span class="sxs-lookup"><span data-stu-id="8c0cf-112">However, they are not affected by the multisite functionality.</span></span>

<span data-ttu-id="8c0cf-113">Följande figur illustrerar hur huvudplaneringen fortskrider.</span><span class="sxs-lookup"><span data-stu-id="8c0cf-113">The following graphic illustrates how master planning proceeds.</span></span> <span data-ttu-id="8c0cf-114">Parametrarna som refereras i bilden och deras siter är som följer:</span><span class="sxs-lookup"><span data-stu-id="8c0cf-114">The parameters that are referred to in the graphic, and their locations, are as follows:</span></span>
-   <span data-ttu-id="8c0cf-115">Lagret har inställningen **Manuellt**.</span><span class="sxs-lookup"><span data-stu-id="8c0cf-115">The warehouse is set to **Manual**.</span></span> <span data-ttu-id="8c0cf-116">Klick på **Lagerhantering &gt; Inställningar &gt; Lagerindelning &gt; Lagerställen**.</span><span class="sxs-lookup"><span data-stu-id="8c0cf-116">Click **Inventory management &gt; Setup &gt; Inventory breakdown &gt; Warehouses**.</span></span> <span data-ttu-id="8c0cf-117">Se fältet **Manuell** på snabbfliken **Huvudplanering**.</span><span class="sxs-lookup"><span data-stu-id="8c0cf-117">On the **Master planning** FastTab, see the **Manual** field.</span></span>
-   <span data-ttu-id="8c0cf-118">Disponeringsplanering har definierats för artikeln.</span><span class="sxs-lookup"><span data-stu-id="8c0cf-118">Item coverage is defined for the item.</span></span> <span data-ttu-id="8c0cf-119">Klicka på **Hantering av produktinformation &gt; Produkter&gt; Frisläppta produkter**.</span><span class="sxs-lookup"><span data-stu-id="8c0cf-119">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="8c0cf-120">Markera artikeln och sedan, i åtgärdsfönstret, på fliken **Plan**, klickar du på **Artikeldisponering**.</span><span class="sxs-lookup"><span data-stu-id="8c0cf-120">Select the item, and then, on the Action pane, on the **Plan** tab, click **Item coverage**.</span></span>
-   <span data-ttu-id="8c0cf-121">Påfyllningsrelationer har definierats för lagret.</span><span class="sxs-lookup"><span data-stu-id="8c0cf-121">Refill relations are defined for the warehouse.</span></span> <span data-ttu-id="8c0cf-122">Klick på **Lagerhantering &gt; Inställningar &gt; Lagerindelning &gt; Lagerställen**.</span><span class="sxs-lookup"><span data-stu-id="8c0cf-122">Click **Inventory management &gt; Setup &gt; Inventory breakdown &gt; Warehouses**.</span></span> <span data-ttu-id="8c0cf-123">Gå till snabbfliken **Huvudplanering** och leta reda på fältgruppen **Huvudlagerställe**.</span><span class="sxs-lookup"><span data-stu-id="8c0cf-123">On the **Master planning** FastTab, see the **Main warehouse** field group.</span></span>
-   <span data-ttu-id="8c0cf-124">Standardordertypen anges som Produktion, Inköpsorder eller Kanban.</span><span class="sxs-lookup"><span data-stu-id="8c0cf-124">The default order type is set to Production, Purchase order, or Kanban.</span></span> <span data-ttu-id="8c0cf-125">Klicka på **Hantering av produktinformation &gt; Produkter&gt; Frisläppta produkter**.</span><span class="sxs-lookup"><span data-stu-id="8c0cf-125">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="8c0cf-126">Markera artikeln och sedan, i åtgärdsfönstret, på fliken **Plan**, klickar du på **Standardorderinställningar**.</span><span class="sxs-lookup"><span data-stu-id="8c0cf-126">Select the item, and then, on the Action pane, on the **Plan** tab, click **Default order settings**.</span></span> <span data-ttu-id="8c0cf-127">Se **Standardordertyp** i formuläret **Standardorderinställningar**.</span><span class="sxs-lookup"><span data-stu-id="8c0cf-127">In the **Default order settings** form, see the **Default order type**.</span></span>

![Efterfrågenedbrytning för täckning av site och lagerställe, lagerställe obligatoriskt](./media/multisitedemandexplosionscenarioforsiteandwarehousecoveragewarehousemandatory.jpg)



<a name="additional-resources"></a><span data-ttu-id="8c0cf-129">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="8c0cf-129">Additional resources</span></span>
--------

[<span data-ttu-id="8c0cf-130">Huvudplanering och multisitefunktioner</span><span class="sxs-lookup"><span data-stu-id="8c0cf-130">Master planning and multisite functionality</span></span>](master-plan-multisite-functionality.md)

[<span data-ttu-id="8c0cf-131">Huvudplanering - platstäckning, lagerställe obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="8c0cf-131">Master planning - site coverage, warehouse mandatory</span></span>](master-plan-site-coverage-warehouse-mandatory.md)

[<span data-ttu-id="8c0cf-132">Huvudplanering - täckning av site, lagerställe ej obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="8c0cf-132">Master planning - site coverage, warehouse not mandatory</span></span>](master-plan-site-coverage-warehouse-not-mandatory.md)

[<span data-ttu-id="8c0cf-133">Huvudplanering - täckning av plats och lagerställe, lagerstället är inte obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="8c0cf-133">Master planning - site and warehouse coverage, warehouse not mandatory</span></span>](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[<span data-ttu-id="8c0cf-134">Huvudplanering - hur strukturlisteversionen bestäms</span><span class="sxs-lookup"><span data-stu-id="8c0cf-134">Master planning - How the BOM version is determined</span></span>](master-plan-bom-version-determined.md)



