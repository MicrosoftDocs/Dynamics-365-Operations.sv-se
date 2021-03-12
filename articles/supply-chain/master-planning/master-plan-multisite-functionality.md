---
title: Huvudplanering och multisitefunktioner – översikt
description: Huvudplanering tar hänsyn till inställningarna för lagerdimensionerna för site och lagerställe.
author: roxanadiaconu
manager: tfehr
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventLocation, InventSite
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2434
ms.assetid: 7f05c031-a446-4168-8cce-03a6305f5c4d
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c42fbd42288a072803e4f5de46560d13129515db
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "5005162"
---
# <a name="master-planning-and-multisite-functionality-overview"></a><span data-ttu-id="c87f3-103">Huvudplanering och multisitefunktioner – översikt</span><span class="sxs-lookup"><span data-stu-id="c87f3-103">Master planning and multisite functionality overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c87f3-104">Huvudplanering tar hänsyn till inställningarna för lagerdimensionerna för site och lagerställe.</span><span class="sxs-lookup"><span data-stu-id="c87f3-104">Master planning takes the settings of the site and warehouse inventory dimensions into account.</span></span> 

<span data-ttu-id="c87f3-105">Platsdimensionen är obligatorisk och du kan ange att lagerställedimensionen ska vara obligatorisk.</span><span class="sxs-lookup"><span data-stu-id="c87f3-105">The site dimension is mandatory, and you can set the warehouse dimension to be mandatory.</span></span>

<span data-ttu-id="c87f3-106">Om en dimension är obligatorisk måste ett dimensionsvärde anges för alla lagertransaktioner.</span><span class="sxs-lookup"><span data-stu-id="c87f3-106">When a dimension is mandatory, a dimension value must be entered on all inventory transactions.</span></span> <span data-ttu-id="c87f3-107">Detta innebär att platsen och lagerstället för den ursprungliga efterfrågan är känd under huvudplaneringen.</span><span class="sxs-lookup"><span data-stu-id="c87f3-107">Therefore, during master planning, the site and the warehouse for the initial demand are known.</span></span> <span data-ttu-id="c87f3-108">Sitedimensionen är också bestående, vilket innebär att sitevärdet inte ändras under nedbrytningen av efterfrågan på lägre nivåer.</span><span class="sxs-lookup"><span data-stu-id="c87f3-108">The site dimension is also consistent so that during the explosion of lower-level demand, the site value does not change.</span></span>

<span data-ttu-id="c87f3-109">Om lagerställedimensionen inte anges som obligatorisk kan det hända att lagerstället är okänt i den ursprungliga efterfrågan.</span><span class="sxs-lookup"><span data-stu-id="c87f3-109">When the warehouse is not set to mandatory, it may not be known from the initial demand.</span></span> <span data-ttu-id="c87f3-110">Planeringsmotorn måste då identifiera vilket lagerställe som ska användas utifrån de inställningar som har definierats för artikeln, enskilda lagerställen och informationen på orderraden.</span><span class="sxs-lookup"><span data-stu-id="c87f3-110">The planning engine must determine which warehouse to use based on the settings that are defined for the item, individual warehouses, and the details of the order line.</span></span>

<span data-ttu-id="c87f3-111">I följande avsnitt beskrivs hur planeringsmotorn används för att avgöra vilket lagerställe som ska användas när olika inställningar har angetts.</span><span class="sxs-lookup"><span data-stu-id="c87f3-111">The following topics describe how the planning engine works, when different settings are defined, to determine the warehouse to use.</span></span>

[<span data-ttu-id="c87f3-112">Huvudplanering för plats och lagerställe, lagerställe obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="c87f3-112">Master planning for site and warehouse coverage, warehouse mandatory</span></span>](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[<span data-ttu-id="c87f3-113">Huvudplanering för täckning av plats, lagerställe obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="c87f3-113">Master planning for site coverage, mandatory warehouse</span></span>](master-plan-site-coverage-warehouse-mandatory.md)

[<span data-ttu-id="c87f3-114">Huvudplanering för plats och lagerställe, lagerställe inte obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="c87f3-114">Master planning for site and warehouse coverage, warehouse not mandatory</span></span>](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[<span data-ttu-id="c87f3-115">Huvudplanering för täckning av plats, lagerställe inte obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="c87f3-115">Master planning for site coverage, warehouse not mandatory</span></span>](master-plan-site-coverage-warehouse-not-mandatory.md)

[<span data-ttu-id="c87f3-116">Avgör strukturlisteversion</span><span class="sxs-lookup"><span data-stu-id="c87f3-116">Determine the BOM version</span></span>](master-plan-bom-version-determined.md)



