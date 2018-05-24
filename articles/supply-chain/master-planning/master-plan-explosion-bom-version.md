---
title: Nedbrytning av en strukturlisteversion
description: "Den här artikeln förklarar ett övergripande planeringsscenario som omfattar nedbrytning av en strukturlista (BOM)."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqTransExplosion
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 19211
ms.assetid: fe08c2e6-9cc5-4e34-bbb2-cd07843403b5
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 80c9fa6ec98bd2cdc3edd5329e2a619ef9cc8cb2
ms.contentlocale: sv-se
ms.lasthandoff: 05/08/2018

---

# <a name="explosion-of-a-bom-version"></a><span data-ttu-id="6bb4b-103">Nedbrytning av en strukturlisteversion</span><span class="sxs-lookup"><span data-stu-id="6bb4b-103">Explosion of a BOM version</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6bb4b-104">Den här artikeln förklarar ett övergripande planeringsscenario som omfattar nedbrytning av en strukturlista (BOM).</span><span class="sxs-lookup"><span data-stu-id="6bb4b-104">This article explains a master planning scenario that involves explosion of a bill of materials (BOM) version.</span></span>

<span data-ttu-id="6bb4b-105">En efterfrågenedbrytning av en strukturlisteversion skapar en efterfrågan för varje artikelrad i strukturlistan på en viss site och kanske ett särskilt lager.</span><span class="sxs-lookup"><span data-stu-id="6bb4b-105">A demand explosion of a bill of materials (BOM) version creates a demand for each BOM line item at a specific site and, possibly, at a specific warehouse.</span></span> <span data-ttu-id="6bb4b-106">I en sitespecifik strukturlista kan ett visst lager definieras för varje strukturlisterad.</span><span class="sxs-lookup"><span data-stu-id="6bb4b-106">In a site-specific BOM, a specific warehouse can be defined for each BOM line.</span></span> <span data-ttu-id="6bb4b-107">Dessutom bestämmer artikeldimensionens inställningar huruvida lagret krävs för varje strukturlisterad.</span><span class="sxs-lookup"><span data-stu-id="6bb4b-107">Additionally, for each BOM line, the item's dimension settings determine whether the warehouse is required.</span></span> <span data-ttu-id="6bb4b-108">Den resulterande efterfrågan för varje strukturlisterad blir i sin tur utgångspunkten för en vidare efterfrågenedbrytning.</span><span class="sxs-lookup"><span data-stu-id="6bb4b-108">The resulting demand for each BOM line item then becomes the starting point for additional demand explosion.</span></span> <span data-ttu-id="6bb4b-109">Det här huvudplaneringsscenariot omfattar följande villkor:</span><span class="sxs-lookup"><span data-stu-id="6bb4b-109">This master planning scenario involves the following conditions:</span></span>

-   <span data-ttu-id="6bb4b-110">Sitedimensionen är obligatorisk och måste anges på efterfrågetransaktionen.</span><span class="sxs-lookup"><span data-stu-id="6bb4b-110">The site dimension is mandatory and must be entered on the demand transaction.</span></span>
-   <span data-ttu-id="6bb4b-111">Sitedimensionen är konsekvent.</span><span class="sxs-lookup"><span data-stu-id="6bb4b-111">The site dimension is consistent.</span></span> <span data-ttu-id="6bb4b-112">Därför är siten för efterfrågan på lägre nivåer densamma som siten för den ursprungliga efterfrågetransaktionen.</span><span class="sxs-lookup"><span data-stu-id="6bb4b-112">Therefore, the site for lower-level demand is the same as the site on the initial demand transaction.</span></span>

<span data-ttu-id="6bb4b-113">Följande bild visar hur processen för efterfrågenedbrytningen i huvudplaneringen fortskrider.</span><span class="sxs-lookup"><span data-stu-id="6bb4b-113">The following illustration shows how the process for master planning demand explosion.</span></span> ![Efterfrågenedbrytning med hjälp av strukturlisteversion](./media/multisitedemandexplosionscenariousingbomversion.gif)

<a name="additional-resources"></a><span data-ttu-id="6bb4b-115">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="6bb4b-115">Additional resources</span></span>
--------

[<span data-ttu-id="6bb4b-116">Huvudplanering - hur strukturlisteversionen bestäms</span><span class="sxs-lookup"><span data-stu-id="6bb4b-116">Master planning - how the BOM version is determined</span></span>](master-plan-bom-version-determined.md)

[<span data-ttu-id="6bb4b-117">Huvudplanering och multisitefunktioner</span><span class="sxs-lookup"><span data-stu-id="6bb4b-117">Master planning and multisite functionality</span></span>](master-plan-multisite-functionality.md)




