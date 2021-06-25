---
title: Huvudplanering för täckning av plats och lagerställe ej obligatoriskt
description: Det här avsnittet innehåller en beskrivning av hur en artikel som har webbplatsen som disponeringsdimension planeras.
author: roxanadiaconu
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResStorageDimensionGroup, ReqItemTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2474
ms.assetid: 316da918-67ae-43c5-baea-00ae559e29b0
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0b306fec702f608d00c3459cecd957eb251361c0
ms.sourcegitcommit: ff09736563d3cd2bc74c7664edd1767b218401cb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "6187588"
---
# <a name="master-planning-for-site-coverage-warehouse-not-mandatory"></a><span data-ttu-id="6eaf4-103">Huvudplanering för täckning av plats och lagerställe ej obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="6eaf4-103">Master planning for site coverage, warehouse not mandatory</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6eaf4-104">Det här avsnittet innehåller en beskrivning av hur en artikel som har webbplatsen som disponeringsdimension planeras.</span><span class="sxs-lookup"><span data-stu-id="6eaf4-104">This topic describes how an item that has the site dimension set for coverage is planned.</span></span>

<span data-ttu-id="6eaf4-105">Det här huvudplaneringsscenariot omfattar följande villkor:</span><span class="sxs-lookup"><span data-stu-id="6eaf4-105">This master planning scenario involves the following conditions:</span></span>

-   <span data-ttu-id="6eaf4-106">Dimensionen på en site är obligatorisk och måste anges på efterfrågetransaktionen.</span><span class="sxs-lookup"><span data-stu-id="6eaf4-106">The site dimension is set to mandatory and must be entered on the demand transaction.</span></span>
-   <span data-ttu-id="6eaf4-107">Lagerdimensionen har inte angetts vara obligatorisk.</span><span class="sxs-lookup"><span data-stu-id="6eaf4-107">The warehouse dimension is not set to mandatory.</span></span> <span data-ttu-id="6eaf4-108">Lagret kan vara känt, men det används inte vid beräkningen av huvudplaneringen.</span><span class="sxs-lookup"><span data-stu-id="6eaf4-108">The warehouse may be known, but it is not used in the master planning calculation.</span></span>
-   <span data-ttu-id="6eaf4-109">Sitedimensionen är aktiverad för disponeringsplanering.</span><span class="sxs-lookup"><span data-stu-id="6eaf4-109">The site dimension is set for coverage planning.</span></span>
-   <span data-ttu-id="6eaf4-110">Lagerställedimensionen är inte aktiverad för disponeringsplanering.</span><span class="sxs-lookup"><span data-stu-id="6eaf4-110">The warehouse dimension is not set for coverage planning.</span></span> <span data-ttu-id="6eaf4-111">Därför sammanställs tillgång och efterfrågan per site, och eventuellt, andra disponeringsplanerade dimensioner.</span><span class="sxs-lookup"><span data-stu-id="6eaf4-111">Therefore, supply and demand are aggregated by site and, perhaps, other coverage-planned dimensions also.</span></span>

<span data-ttu-id="6eaf4-112">Följande figur illustrerar hur huvudplaneringen fortskrider.</span><span class="sxs-lookup"><span data-stu-id="6eaf4-112">The following graphic illustrates how master planning proceeds.</span></span> <span data-ttu-id="6eaf4-113">Parametrarna som refereras i bilden och deras siter är som följer:</span><span class="sxs-lookup"><span data-stu-id="6eaf4-113">The parameters that are referred to in the graphic, and their locations, are as follows:</span></span>
-   <span data-ttu-id="6eaf4-114">Disponeringsplanering har definierats för artikeln.</span><span class="sxs-lookup"><span data-stu-id="6eaf4-114">Item coverage is defined for the item.</span></span> <span data-ttu-id="6eaf4-115">Klicka på **Hantering av produktinformation &gt; Produkter&gt; Frisläppta produkter**.</span><span class="sxs-lookup"><span data-stu-id="6eaf4-115">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="6eaf4-116">Markera artikeln och klicka sedan på **Plan &gt; Artikeldisponering**.</span><span class="sxs-lookup"><span data-stu-id="6eaf4-116">Select the item, and then click **Plan &gt; Item coverage**.</span></span>
-   <span data-ttu-id="6eaf4-117">Påfyllningsrelationer har definierats för lagret.</span><span class="sxs-lookup"><span data-stu-id="6eaf4-117">Refill relations are defined for the warehouse.</span></span> <span data-ttu-id="6eaf4-118">Klick på **Lagerhantering &gt; Inställningar &gt; Lagerindelning &gt; Lagerställen**.</span><span class="sxs-lookup"><span data-stu-id="6eaf4-118">Click **Inventory management &gt; Setup &gt; Inventory breakdown &gt; Warehouses**.</span></span> <span data-ttu-id="6eaf4-119">Gå till fliken **Huvudplanering** och leta reda på fältgruppen **Huvudlagerställe**.</span><span class="sxs-lookup"><span data-stu-id="6eaf4-119">On the **Master planning** tab, see the **Main warehouse** field group.</span></span>
-   <span data-ttu-id="6eaf4-120">Standardordertypen anges som Produktion, Inköpsorder eller Kanban.</span><span class="sxs-lookup"><span data-stu-id="6eaf4-120">The default order type is set to Production, Purchase order or Kanban.</span></span> <span data-ttu-id="6eaf4-121">Klicka på **Hantering av produktinformation &gt; Produkter&gt; Frisläppta produkter**.</span><span class="sxs-lookup"><span data-stu-id="6eaf4-121">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="6eaf4-122">Välj artikeln och klicka sedan på **Plan &gt; Standardorderinställningar**.</span><span class="sxs-lookup"><span data-stu-id="6eaf4-122">Select the item, and then click **Plan &gt; Default order settings**.</span></span> <span data-ttu-id="6eaf4-123">I formuläret **Standardorderinställningar**, se fältet **Standardordertyp** .</span><span class="sxs-lookup"><span data-stu-id="6eaf4-123">In the **Default order settings** form, see the **Default order type** field.</span></span>

![Efterfrågenedbrytning för täckning av site, lagerställe ej obligatoriskt    ](./media/multisitedemandexplosionscenarioforsitecoveragewarehousenotmandatory.jpg)



## <a name="additional-resources"></a><span data-ttu-id="6eaf4-125">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="6eaf4-125">Additional resources</span></span>

[<span data-ttu-id="6eaf4-126">Huvudplanering och multisitefunktioner – översikt</span><span class="sxs-lookup"><span data-stu-id="6eaf4-126">Master planning and multisite functionality overview</span></span>](master-plan-multisite-functionality.md)

[<span data-ttu-id="6eaf4-127">Huvudplanering för plats och lagerställe, lagerställe obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="6eaf4-127">Master planning for site and warehouse coverage, warehouse mandatory</span></span>](master-plan-site-coverage-warehouse-mandatory.md)

[<span data-ttu-id="6eaf4-128">Huvudplanering för täckning av plats, lagerställe obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="6eaf4-128">Master planning for site coverage, mandatory warehouse</span></span>](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[<span data-ttu-id="6eaf4-129">Huvudplanering för täckning av plats, lagerställe inte obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="6eaf4-129">Master planning for site coverage, warehouse not mandatory</span></span>](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[<span data-ttu-id="6eaf4-130">Avgör strukturlisteversion</span><span class="sxs-lookup"><span data-stu-id="6eaf4-130">Determine the BOM version</span></span>](master-plan-bom-version-determined.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]