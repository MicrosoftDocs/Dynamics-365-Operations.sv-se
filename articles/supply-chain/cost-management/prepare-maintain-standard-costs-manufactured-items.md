---
title: Förbereda underhåll av standardkostnader för tillverkade artiklar
description: Det här avsnittet beskriver hur du förbereder för underhåll av kostnader för tillverkade artiklar.
author: AndersGirke
manager: tfehr
ms.date: 01/17/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventStdCostConv
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f428f2e3966155b4fc95fd94b6a55d059eb3533d
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5263528"
---
# <a name="prepare-to-maintain-standard-costs-for-manufactured-items"></a><span data-ttu-id="184fe-103">Förbereda underhåll av standardkostnader för tillverkade artiklar</span><span class="sxs-lookup"><span data-stu-id="184fe-103">Prepare to maintain standard costs for manufactured items</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="184fe-104">Det här avsnittet beskriver hur du förbereder för underhåll av kostnader för tillverkade artiklar.</span><span class="sxs-lookup"><span data-stu-id="184fe-104">This topic describes the steps for preparing to maintain costs for manufactured items.</span></span> <span data-ttu-id="184fe-105">Hur du gör för tillverkade artiklar skiljer sig något från hur du gör för inköpta artiklar.</span><span class="sxs-lookup"><span data-stu-id="184fe-105">The steps for manufactured items differ slightly from the steps for purchased items.</span></span>

<span data-ttu-id="184fe-106">De principer som tilldelas tillverkade artiklar kan påverka kostnadsberäkningarna för de överordnade tillverkade artiklarna.</span><span class="sxs-lookup"><span data-stu-id="184fe-106">Policies that are assigned to manufactured items can affect the cost calculations for the parent manufactured items.</span></span> <span data-ttu-id="184fe-107">För att förbereda underhåll av kostnader för tillverkade artiklar följ dessa steg:</span><span class="sxs-lookup"><span data-stu-id="184fe-107">To prepare to maintain costs for manufactured items, follow these steps.</span></span>

1. <span data-ttu-id="184fe-108">Tilldela en artikelmodellgrupp till den tillverkade artikeln.</span><span class="sxs-lookup"><span data-stu-id="184fe-108">Assign an item model group to the manufactured item.</span></span> 

   <span data-ttu-id="184fe-109">Artikelmodellgruppen identifierar att standardkostnaderna ska användas.</span><span class="sxs-lookup"><span data-stu-id="184fe-109">The item model group identifies that standard costs will be used.</span></span>

2. <span data-ttu-id="184fe-110">Tilldela en artikelgrupp till den tillverkade artikeln.</span><span class="sxs-lookup"><span data-stu-id="184fe-110">Assign an item group to the manufactured item.</span></span> 

   <span data-ttu-id="184fe-111">Artikelgruppen innehåller de redovisningskonton som gäller för den tillverkade artikeln.</span><span class="sxs-lookup"><span data-stu-id="184fe-111">The item group contains ledger accounts that apply to the manufactured item.</span></span> <span data-ttu-id="184fe-112">Redovisningskontona för en tillverkad artikel som har lagermodellen standardkostnad omfattar flera produktionsavvikelser, kostnadsändringsavvikelsen och omvärderingen av lagerkostnad.</span><span class="sxs-lookup"><span data-stu-id="184fe-112">The ledger accounts for a manufactured item that has a standard cost inventory model include several production variances, the cost change variance, and the inventory cost revaluation.</span></span>

3. <span data-ttu-id="184fe-113">Tilldela lagermåttet till artikeln.</span><span class="sxs-lookup"><span data-stu-id="184fe-113">Assign the inventory unit of measure to the item.</span></span> 

   <span data-ttu-id="184fe-114">Artikelns kostnader uttrycks alltid i artikelns lagermåttenhet.</span><span class="sxs-lookup"><span data-stu-id="184fe-114">The item's costs are always expressed in the item's inventory unit of measure.</span></span>

4. <span data-ttu-id="184fe-115">Tilldela inte en kostnadsgrupp till en tillverkad artikel, såvida den inte ska behandlas som en inköpt artikel.</span><span class="sxs-lookup"><span data-stu-id="184fe-115">Don't assign a cost group to the manufactured item unless the item will be treated as a purchased item.</span></span>

5. <span data-ttu-id="184fe-116">Tilldela en strukturlisteberäkningsgrupp till den tillverkade artikeln.</span><span class="sxs-lookup"><span data-stu-id="184fe-116">Assign a bill of materials (BOM) calculation group to the manufactured item.</span></span> 

   <span data-ttu-id="184fe-117">Artikelns strukturlisteberäkningsgrupp definierar de varningsvillkor som gäller.</span><span class="sxs-lookup"><span data-stu-id="184fe-117">The item's BOM calculation group defines warning conditions that apply.</span></span> <span data-ttu-id="184fe-118">På så sätt kan varningsmeddelanden genereras om möjliga orsaker till beräkningsfelet när en strukturlisteberäkning utförs.</span><span class="sxs-lookup"><span data-stu-id="184fe-118">In that way, when a BOM calculation is done, warning messages can be generated about possible sources of calculation errors.</span></span> <span data-ttu-id="184fe-119">Ett varningsmeddelande kan till exempel identifiera när en aktiv strukturlista eller ett flöde inte finns.</span><span class="sxs-lookup"><span data-stu-id="184fe-119">For example, a warning message can identify when an active BOM or route doesn't exist.</span></span> <span data-ttu-id="184fe-120">Beräkningsgruppen för strukturlistan innehåller en princip för att stoppa nedbrytning som anger när en tillverkad artikel borde hanteras som en inköpt artikel.</span><span class="sxs-lookup"><span data-stu-id="184fe-120">The BOM calculation group contains a stop explosion policy that indicates when a manufactured item should be treated as a purchased item.</span></span>

6. <span data-ttu-id="184fe-121">Tilldela en standardorderkvantitet till den tilldelade artikeln om den har konstanta kostnader.</span><span class="sxs-lookup"><span data-stu-id="184fe-121">If the manufactured item has constant costs, assign a standard order quantity to it.</span></span> 

   <span data-ttu-id="184fe-122">Standardorderkvantiteten är en redovisningspartistorlek för amortering av konstanta kostnader.</span><span class="sxs-lookup"><span data-stu-id="184fe-122">The standard order quantity is an accounting lot size for amortizing constant costs.</span></span> <span data-ttu-id="184fe-123">Exempel på konstanta kostnader inkluderar inställningstider i flödesoperationer och en konstant komponentkvantitet i en strukturlista (BOM).</span><span class="sxs-lookup"><span data-stu-id="184fe-123">Examples of constant costs include setup times in routing operations and a constant component quantity in the BOM.</span></span>

7. <span data-ttu-id="184fe-124">Definiera strukturlistan för den tillverkade artikeln.</span><span class="sxs-lookup"><span data-stu-id="184fe-124">Define the BOM for the manufactured item.</span></span> 

   <span data-ttu-id="184fe-125">Du kan definiera en eller flera strukturlisteversioner för den tillverkade artikeln.</span><span class="sxs-lookup"><span data-stu-id="184fe-125">One or more BOM versions can be defined for the manufactured item.</span></span> <span data-ttu-id="184fe-126">Kontrollera att de versioner som du vill använda har markerats som godkända och aktiva och att de har önskade giltighetsdatum.</span><span class="sxs-lookup"><span data-stu-id="184fe-126">Verify that the versions that you want have been marked as approved and active, and that they have the effective dates that you want.</span></span> <span data-ttu-id="184fe-127">Strukturlisteversionen kan gälla för hela företaget eller för en viss site.</span><span class="sxs-lookup"><span data-stu-id="184fe-127">The BOM version can be company-wide or site-specific.</span></span>

8. <span data-ttu-id="184fe-128">Definiera flödet för den tillverkade artikeln.</span><span class="sxs-lookup"><span data-stu-id="184fe-128">Define the routing for the manufactured item.</span></span> 

   <span data-ttu-id="184fe-129">Du kan definiera en eller flera flödesversioner för den tillverkade artikeln.</span><span class="sxs-lookup"><span data-stu-id="184fe-129">One or more route versions can be defined for the manufactured item.</span></span> <span data-ttu-id="184fe-130">Kontrollera att de versioner som du vill använda har markerats som godkända och aktiva och att de har önskade giltighetsdatum.</span><span class="sxs-lookup"><span data-stu-id="184fe-130">Verify that the versions that you want have been marked as approved and active, and that they have the effective dates that you want.</span></span> <span data-ttu-id="184fe-131">Flödesversionen måste gälla för en viss site.</span><span class="sxs-lookup"><span data-stu-id="184fe-131">The route version must be site-specific.</span></span>

<span data-ttu-id="184fe-132">Om du vill använda flödesinformation i kostnadssyfte krävs ytterligare förberedelser.</span><span class="sxs-lookup"><span data-stu-id="184fe-132">If you want to use routing information for costing purposes, additional preparation steps are required.</span></span> <span data-ttu-id="184fe-133">Till exempel måste de kostnadskategorier som tilldelas flödesoperationer vara korrekta och fullständiga.</span><span class="sxs-lookup"><span data-stu-id="184fe-133">For example, the cost categories that are assigned to routing operations must be correct and completed.</span></span>

<a name="related-topics"></a><span data-ttu-id="184fe-134">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="184fe-134">Related topics</span></span>
--------

[<span data-ttu-id="184fe-135">Periodisera konstanta kostnader för en tillverkad artikel</span><span class="sxs-lookup"><span data-stu-id="184fe-135">Amortize constant costs for a manufactured item</span></span>](amortize-constant-costs-manufactured-item.md)

[<span data-ttu-id="184fe-136">Ställ in produkter som antingen kan produceras eller anskaffas</span><span class="sxs-lookup"><span data-stu-id="184fe-136">Set up products that can be produced or procured</span></span>](manufactured-items-treated-as-purchased-items.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]