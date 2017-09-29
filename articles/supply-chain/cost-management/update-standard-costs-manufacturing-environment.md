---
title: "Uppdatera standardkostnader i en tillverkningsmiljö"
description: "Det här avsnittet ger vägledning om hur du uppdaterar standardkostnader i en tillverkningsmiljö."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CostingVersion, InventStdCostConv
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 79663
ms.assetid: 3a7c3d13-8dbc-442d-a281-ac0ebe99ec83
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 7a5340baad38864388abcfab3235cf459887cba9
ms.contentlocale: sv-se
ms.lasthandoff: 07/18/2017

---

# <a name="update-standard-costs-in-a-manufacturing-environment"></a><span data-ttu-id="f5661-103">Uppdatera standardkostnader i en tillverkningsmiljö</span><span class="sxs-lookup"><span data-stu-id="f5661-103">Update standard costs in a manufacturing environment</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="f5661-104">Det här avsnittet ger vägledning om hur du uppdaterar standardkostnader i en tillverkningsmiljö.</span><span class="sxs-lookup"><span data-stu-id="f5661-104">This article provides guidance about how to update standard costs in a manufacturing environment.</span></span> 

<span data-ttu-id="f5661-105">Uppdateringar kan återspegla nya artiklar, kostnadskategorier eller beräkningsformler för indirekta kostnader.</span><span class="sxs-lookup"><span data-stu-id="f5661-105">Updates can reflect new items, cost categories, or indirect cost calculation formulas.</span></span> <span data-ttu-id="f5661-106">De kan också återspegla korrigeringar och kostnadsförändringar.</span><span class="sxs-lookup"><span data-stu-id="f5661-106">They can also reflect corrections and cost changes.</span></span> <span data-ttu-id="f5661-107">Typen av uppdatering påverkar vilka steg som måste slutföras för att uppdatera standardkostnader, vilket visas i exemplen nedan.</span><span class="sxs-lookup"><span data-stu-id="f5661-107">The type of update affects the steps that you must complete to update standard costs, as illustrated in the following cases:</span></span>

-   <span data-ttu-id="f5661-108">Ange förväntade standardkostnadsändringar för inköpta artiklar och ändra sedan status för artikelkostnadsposterna till **Aktiv** på lämpligt datum.</span><span class="sxs-lookup"><span data-stu-id="f5661-108">Enter expected standard cost changes for purchased items, and then change the status of the item cost records to **Active** on the appropriate date.</span></span> <span data-ttu-id="f5661-109">Du ska däremot inte beräkna om kostnaderna för tillverkade artiklar som använder de inköpta artiklarna.</span><span class="sxs-lookup"><span data-stu-id="f5661-109">However, don't recalculate the costs of manufactured items that use the purchased items.</span></span>
-   <span data-ttu-id="f5661-110">Ange standardkostnader för en ny inköpt artikel, men beräkna inte om kostnaderna för tillverkade artiklar som har en strukturlisteversion (BOM) som innehåller den nya inköpta artikeln som en komponent.</span><span class="sxs-lookup"><span data-stu-id="f5661-110">Enter standard costs for a new purchased item, but don't recalculate the costs of manufactured items that have a bill of materials (BOM) version that contains the new purchased item as a component.</span></span>
-   <span data-ttu-id="f5661-111">Korrigera eller ändra kostnaden för en inköpt artikel eller ändra kostnadsgruppen som tilldelats en inköpt artikel och beräkna kostnaden för alla tillverkade artiklar som har en strukturlisteversion som innehåller den inköpta artikeln som en komponent.</span><span class="sxs-lookup"><span data-stu-id="f5661-111">Correct or change the cost of a purchased item, or change the cost group that is assigned to a purchased item, and calculate the cost for all manufactured items that have a BOM version that contains the purchased item as a component.</span></span>
-   <span data-ttu-id="f5661-112">Ändra kostnaden för en kostnadskategori och beräkna om kostnaden för alla tillverkade artiklar som har en flödesversion som innehåller flödesoperationer som använder den kostnadskategorin.</span><span class="sxs-lookup"><span data-stu-id="f5661-112">Change the cost for a cost category, and calculate the cost for all manufactured items that have a route version that contains routing operations that use the cost category.</span></span>
-   <span data-ttu-id="f5661-113">Ändra kostnadskategorierna som tilldelats till flödesåtgärderna eller den kostnadskalkylerade gruppen som tilldelats till kostnadskategorier.</span><span class="sxs-lookup"><span data-stu-id="f5661-113">Change the cost categories that are assigned to routing operations or the cost group that is assigned to cost categories.</span></span> <span data-ttu-id="f5661-114">Beräkna sedan kostnaden för en alla tillverkade artiklar som har en flödesversion som innehåller flödesoperationer som använder den kostnadskategorin.</span><span class="sxs-lookup"><span data-stu-id="f5661-114">Then calculate the cost for all manufactured items that have a route version that contains routing operations that use the cost category.</span></span>
-   <span data-ttu-id="f5661-115">Ändra en beräkningsformel för indirekt kostnad, och beräkna kostnaden för alla tillverkade artiklar som påverkas av ändringen.</span><span class="sxs-lookup"><span data-stu-id="f5661-115">Change an indirect cost calculation formula, and calculate the cost for all manufactured items that are affected by the change.</span></span>
-   <span data-ttu-id="f5661-116">Ändra eller lägga till en tillverkningssite för en tillverkad artikel, och beräkna artikelns tillverkningskostnad för siten.</span><span class="sxs-lookup"><span data-stu-id="f5661-116">Change or add a manufacturing site for a manufactured item, and calculate the item's manufactured cost for the site.</span></span>
-   <span data-ttu-id="f5661-117">Beräkna (eller beräkna om) kostnaden för en tillverkad artikel och beräkna om kostnaden för alla tillverkade artiklar som har en strukturlisteversion som innehåller den tillverkade artikeln som en komponent.</span><span class="sxs-lookup"><span data-stu-id="f5661-117">Calculate, or recalculate, the cost for a manufactured item, and recalculate the cost for all manufactured items that have a BOM version that contains the manufactured item as a component.</span></span>
-   <span data-ttu-id="f5661-118">Beräkna kostnader för en ny tillverkad artikel baserat på dess definierade, godkända och aktiva strukturlista och flödesinformation.</span><span class="sxs-lookup"><span data-stu-id="f5661-118">Calculate costs for a new manufactured item, based on its defined, approved, and active BOM and route information.</span></span>

<span data-ttu-id="f5661-119">I varje fall bör du noggrant överväga hur du ska uppdatera standardkostnader.</span><span class="sxs-lookup"><span data-stu-id="f5661-119">Each case requires careful consideration about how to update standard costs.</span></span>




