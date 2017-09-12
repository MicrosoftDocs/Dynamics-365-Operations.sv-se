---
title: "Huvudplanering för täckning av plats och lagerställe ej obligatoriskt"
description: "Det här avsnittet innehåller en beskrivning av hur en artikel som har webbplatsen som disponeringsdimension planeras."
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
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 2474
ms.assetid: 316da918-67ae-43c5-baea-00ae559e29b0
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 79582e92daeaf0afb032448d36be12edd0926089
ms.contentlocale: sv-se
ms.lasthandoff: 08/29/2017

---

# <a name="master-planning-for-site-coverage-warehouse-not-mandatory"></a><span data-ttu-id="38052-103">Huvudplanering för täckning av plats och lagerställe ej obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="38052-103">Master planning for site coverage, warehouse not mandatory</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="38052-104">Det här avsnittet innehåller en beskrivning av hur en artikel som har webbplatsen som disponeringsdimension planeras.</span><span class="sxs-lookup"><span data-stu-id="38052-104">This topic describes how an item that has the site dimension set for coverage is planned.</span></span>

<span data-ttu-id="38052-105">Det här huvudplaneringsscenariot omfattar följande villkor:</span><span class="sxs-lookup"><span data-stu-id="38052-105">This master planning scenario involves the following conditions:</span></span>

-   <span data-ttu-id="38052-106">Dimensionen på en site är obligatorisk och måste anges på efterfrågetransaktionen.</span><span class="sxs-lookup"><span data-stu-id="38052-106">The site dimension is set to mandatory and must be entered on the demand transaction.</span></span>
-   <span data-ttu-id="38052-107">Lagerdimensionen har inte angetts vara obligatorisk.</span><span class="sxs-lookup"><span data-stu-id="38052-107">The warehouse dimension is not set to mandatory.</span></span> <span data-ttu-id="38052-108">Lagret kan vara känt, men det används inte vid beräkningen av huvudplaneringen.</span><span class="sxs-lookup"><span data-stu-id="38052-108">The warehouse may be known, but it is not used in the master planning calculation.</span></span>
-   <span data-ttu-id="38052-109">Sitedimensionen är aktiverad för disponeringsplanering.</span><span class="sxs-lookup"><span data-stu-id="38052-109">The site dimension is set for coverage planning.</span></span>
-   <span data-ttu-id="38052-110">Lagerställedimensionen är inte aktiverad för disponeringsplanering.</span><span class="sxs-lookup"><span data-stu-id="38052-110">The warehouse dimension is not set for coverage planning.</span></span> <span data-ttu-id="38052-111">Därför sammanställs tillgång och efterfrågan per site, och eventuellt, andra disponeringsplanerade dimensioner.</span><span class="sxs-lookup"><span data-stu-id="38052-111">Therefore, supply and demand are aggregated by site and, perhaps, other coverage-planned dimensions also.</span></span>

<span data-ttu-id="38052-112">Följande figur illustrerar hur huvudplaneringen fortskrider.</span><span class="sxs-lookup"><span data-stu-id="38052-112">The following graphic illustrates how master planning proceeds.</span></span> <span data-ttu-id="38052-113">Parametrarna som refereras i bilden och deras siter är som följer:</span><span class="sxs-lookup"><span data-stu-id="38052-113">The parameters that are referred to in the graphic, and their locations, are as follows:</span></span>
-   <span data-ttu-id="38052-114">Disponeringsplanering har definierats för artikeln.</span><span class="sxs-lookup"><span data-stu-id="38052-114">Item coverage is defined for the item.</span></span> <span data-ttu-id="38052-115">Klicka på **Hantering av produktinformation &gt; Produkter&gt; Frisläppta produkter**.</span><span class="sxs-lookup"><span data-stu-id="38052-115">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="38052-116">Markera artikeln och klicka sedan på **Plan &gt; Artikeldisponering**.</span><span class="sxs-lookup"><span data-stu-id="38052-116">Select the item, and then click **Plan &gt; Item coverage**.</span></span>
-   <span data-ttu-id="38052-117">Påfyllningsrelationer har definierats för lagret.</span><span class="sxs-lookup"><span data-stu-id="38052-117">Refill relations are defined for the warehouse.</span></span> <span data-ttu-id="38052-118">Klick på **Lagerhantering &gt; Inställningar &gt; Lagerindelning &gt; Lagerställen**.</span><span class="sxs-lookup"><span data-stu-id="38052-118">Click **Inventory management &gt; Setup &gt; Inventory breakdown &gt; Warehouses**.</span></span> <span data-ttu-id="38052-119">Gå till fliken **Huvudplanering** och leta reda på fältgruppen **Huvudlagerställe**.</span><span class="sxs-lookup"><span data-stu-id="38052-119">On the **Master planning** tab, see the **Main warehouse** field group.</span></span>
-   <span data-ttu-id="38052-120">Standardordertypen anges som Produktion, Inköpsorder eller Kanban.</span><span class="sxs-lookup"><span data-stu-id="38052-120">The default order type is set to Production, Purchase order or Kanban.</span></span> <span data-ttu-id="38052-121">Klicka på **Hantering av produktinformation &gt; Produkter&gt; Frisläppta produkter**.</span><span class="sxs-lookup"><span data-stu-id="38052-121">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="38052-122">Välj artikeln och klicka sedan på **Plan &gt; Standardorderinställningar**.</span><span class="sxs-lookup"><span data-stu-id="38052-122">Select the item, and then click **Plan &gt; Default order settings**.</span></span> <span data-ttu-id="38052-123">I formuläret **Standardorderinställningar**, se fältet **Standardordertyp** .</span><span class="sxs-lookup"><span data-stu-id="38052-123">In the **Default order settings** form, see the **Default order type** field.</span></span>

![Efterfrågenedbrytning för täckning av site, lagerställe ej obligatoriskt    ](./media/multisitedemandexplosionscenarioforsitecoveragewarehousenotmandatory.jpg)



<a name="see-also"></a><span data-ttu-id="38052-125">Se även</span><span class="sxs-lookup"><span data-stu-id="38052-125">See also</span></span>
--------

[<span data-ttu-id="38052-126">Huvudplanering och multiplatsfunktioner</span><span class="sxs-lookup"><span data-stu-id="38052-126">Master planning and multisite functionality</span></span>](master-plan-multisite-functionality.md)

[<span data-ttu-id="38052-127">Huvudplanering - platstäckning, lagerställe obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="38052-127">Master planning - site coverage, warehouse mandatory</span></span>](master-plan-site-coverage-warehouse-mandatory.md)

[<span data-ttu-id="38052-128">Huvudplanering - täckning av plats och lagerställe, lagerstället är inte obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="38052-128">Master planning - site and warehouse coverage, warehouse not mandatory</span></span>](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[<span data-ttu-id="38052-129">Huvudplanering - täckning av site och lagerställe, lagerställe obligatorisk</span><span class="sxs-lookup"><span data-stu-id="38052-129">Master planning - site and warehouse coverage, warehouse mandatory</span></span>](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[<span data-ttu-id="38052-130">Huvudplanering - hur strukturlisteversionen bestäms</span><span class="sxs-lookup"><span data-stu-id="38052-130">Master planning - how the BOM version is determined</span></span>](master-plan-bom-version-determined.md)




