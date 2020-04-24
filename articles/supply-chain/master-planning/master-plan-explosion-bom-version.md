---
title: Nedbrytning av en strukturlisteversion
description: Den här artikeln förklarar ett övergripande planeringsscenario som omfattar nedbrytning av en strukturlista (BOM).
author: roxanadiaconu
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqTransExplosion
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 19211
ms.assetid: fe08c2e6-9cc5-4e34-bbb2-cd07843403b5
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 380f8069a726e53084164a5ac1fc0a0a99c83590
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "3213755"
---
# <a name="explosion-of-a-bom-version"></a><span data-ttu-id="5aab1-103">Nedbrytning av en strukturlisteversion</span><span class="sxs-lookup"><span data-stu-id="5aab1-103">Explosion of a BOM version</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5aab1-104">Den här artikeln förklarar ett övergripande planeringsscenario som omfattar nedbrytning av en strukturlista (BOM).</span><span class="sxs-lookup"><span data-stu-id="5aab1-104">This article explains a master planning scenario that involves explosion of a bill of materials (BOM) version.</span></span>

<span data-ttu-id="5aab1-105">En efterfrågenedbrytning av en strukturlisteversion skapar en efterfrågan för varje artikelrad i strukturlistan på en viss site och kanske ett särskilt lager.</span><span class="sxs-lookup"><span data-stu-id="5aab1-105">A demand explosion of a bill of materials (BOM) version creates a demand for each BOM line item at a specific site and, possibly, at a specific warehouse.</span></span> <span data-ttu-id="5aab1-106">I en sitespecifik strukturlista kan ett visst lager definieras för varje strukturlisterad.</span><span class="sxs-lookup"><span data-stu-id="5aab1-106">In a site-specific BOM, a specific warehouse can be defined for each BOM line.</span></span> <span data-ttu-id="5aab1-107">Dessutom bestämmer artikeldimensionens inställningar huruvida lagret krävs för varje strukturlisterad.</span><span class="sxs-lookup"><span data-stu-id="5aab1-107">Additionally, for each BOM line, the item's dimension settings determine whether the warehouse is required.</span></span> <span data-ttu-id="5aab1-108">Den resulterande efterfrågan för varje strukturlisterad blir i sin tur utgångspunkten för en vidare efterfrågenedbrytning.</span><span class="sxs-lookup"><span data-stu-id="5aab1-108">The resulting demand for each BOM line item then becomes the starting point for additional demand explosion.</span></span> <span data-ttu-id="5aab1-109">Det här huvudplaneringsscenariot omfattar följande villkor:</span><span class="sxs-lookup"><span data-stu-id="5aab1-109">This master planning scenario involves the following conditions:</span></span>

-   <span data-ttu-id="5aab1-110">Sitedimensionen är obligatorisk och måste anges på efterfrågetransaktionen.</span><span class="sxs-lookup"><span data-stu-id="5aab1-110">The site dimension is mandatory and must be entered on the demand transaction.</span></span>
-   <span data-ttu-id="5aab1-111">Sitedimensionen är konsekvent.</span><span class="sxs-lookup"><span data-stu-id="5aab1-111">The site dimension is consistent.</span></span> <span data-ttu-id="5aab1-112">Därför är siten för efterfrågan på lägre nivåer densamma som siten för den ursprungliga efterfrågetransaktionen.</span><span class="sxs-lookup"><span data-stu-id="5aab1-112">Therefore, the site for lower-level demand is the same as the site on the initial demand transaction.</span></span>

<span data-ttu-id="5aab1-113">Följande bild visar hur processen för efterfrågenedbrytningen i huvudplaneringen fortskrider.</span><span class="sxs-lookup"><span data-stu-id="5aab1-113">The following illustration shows how the process for master planning demand explosion.</span></span> ![Efterfrågenedbrytning med hjälp av strukturlisteversion](./media/multisitedemandexplosionscenariousingbomversion.gif)

<a name="additional-resources"></a><span data-ttu-id="5aab1-115">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="5aab1-115">Additional resources</span></span>
--------

[<span data-ttu-id="5aab1-116">Avgör strukturlisteversion</span><span class="sxs-lookup"><span data-stu-id="5aab1-116">Determine the BOM version</span></span>](master-plan-bom-version-determined.md)

[<span data-ttu-id="5aab1-117">Huvudplanering och multisitefunktioner – översikt</span><span class="sxs-lookup"><span data-stu-id="5aab1-117">Master planning and multisite functionality overview</span></span>](master-plan-multisite-functionality.md)



