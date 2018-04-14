---
title: "Periodisering av konstanta kostnader för en tillverkad artikel"
description: "En tillverkad artikels konstanta kostnader återspeglar driftställtiderna och komponenterna med en konstant kvantitet eller ett konstant kassationsbelopp."
author: AndersGirke
manager: AnnBe
ms.date: 04/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BOMCalcDialog, BOMCalcTable, BOMCalcTrans
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 274503
ms.assetid: 535ab25d-a031-4e8c-84ec-478f2987a1ad
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.dyn365.ops.version: AX 7.0.0
ms.search.validFrom: 2016-02-28
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 2e9d15e35661d37036af48d4d1183e4f25012e57
ms.contentlocale: sv-se
ms.lasthandoff: 04/13/2018

---

# <a name="amortize-constant-costs-for-a-manufactured-item"></a><span data-ttu-id="e2dec-103">Periodisering av konstanta kostnader för en tillverkad artikel</span><span class="sxs-lookup"><span data-stu-id="e2dec-103">Amortize constant costs for a manufactured item</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="e2dec-104">En tillverkad artikels konstanta kostnader återspeglar driftställtiderna och komponenterna med en konstant kvantitet eller ett konstant kassationsbelopp.</span><span class="sxs-lookup"><span data-stu-id="e2dec-104">A manufactured item’s constant costs reflect the operation setup times and the components that have a constant quantity or a constant scrap amount.</span></span> 

<span data-ttu-id="e2dec-105">Begreppet kostnadskalkylerad partistorlek används för att periodisera de konstanta kostnaderna i den beräknade kostnaden för en tillverkad artikel.</span><span class="sxs-lookup"><span data-stu-id="e2dec-105">The concept of a costing lot size is used to amortize these constant costs in the calculated cost of a manufactured item.</span></span> <span data-ttu-id="e2dec-106">Detta begrepp har flera synonymer, varav en är redovisningspartistorlek.</span><span class="sxs-lookup"><span data-stu-id="e2dec-106">This concept has several synonyms, one of which is accounting lot size.</span></span> <span data-ttu-id="e2dec-107">Begreppet periodisering av konstanta kostnader har också flera synonymer, varav en är proportionella konstanta kostnader.</span><span class="sxs-lookup"><span data-stu-id="e2dec-107">The concept of amortizing constant costs also has several synonyms, one of which is proportional constant costs.</span></span>

<span data-ttu-id="e2dec-108">Kostnadskalkylerad partistorlekskvantitet för en tillverkad artikel används i en strukturlisteberäkning.</span><span class="sxs-lookup"><span data-stu-id="e2dec-108">The quantity of a costing lot size for a manufactured item is used in a bill of material (BOM) calculation.</span></span> <span data-ttu-id="e2dec-109">Kvantiteten beror på hur du initierar och utför strukturlisteberäkningen, enligt följande:</span><span class="sxs-lookup"><span data-stu-id="e2dec-109">The quantity depends on how you initiate and perform the BOM calculation, as illustrated by the following:</span></span>

-   <span data-ttu-id="e2dec-110">Standardberäkning av kvantitet i en artikels strukturlisteberäkning − artikelns standardorderkvantitet (för lager) används för kostnadskalkylerad partistorlek, men standardvärdet kan vara en större kvantitet för att avspegla artikelns orderkvantitetsmultipel.</span><span class="sxs-lookup"><span data-stu-id="e2dec-110">Default calculation quantity in an item’s BOM calculation − The item’s standard order quantity for inventory acts as the costing lot size, but the default value might be a greater quantity to reflect the item’s order quantity multiple.</span></span> <span data-ttu-id="e2dec-111">Artikelns standardorderkvantitet och multipel kan definieras i dess standardorderinställningar eller i sitespecifika orderinställningar.</span><span class="sxs-lookup"><span data-stu-id="e2dec-111">The item’s standard order quantity and multiple can be defined within its default order settings or site-specific order settings.</span></span>
-   <span data-ttu-id="e2dec-112">Specificerad beräkningskvantitet i en artikels strukturlisteberäkning − den angivna beräkningskvantiteten fungerar som kostnadskalkylerad partistorlek för artikeln.</span><span class="sxs-lookup"><span data-stu-id="e2dec-112">Specified calculation quantity in an item’s BOM calculation − The specified calculation quantity acts as the costing lot size for the item.</span></span> <span data-ttu-id="e2dec-113">Beräkningskvantiteten anges automatiskt till artikelns standardorderkvantitet, men standardvärdet kan ändras manuellt.</span><span class="sxs-lookup"><span data-stu-id="e2dec-113">The calculation quantity initially uses the item’s standard order quantity, but the default value can be manually overridden.</span></span> <span data-ttu-id="e2dec-114">Den angivna beräkningskvantiteten representerar den kostnadskalkylerade partistorleken för den angivna artikeln och för tillverkade komponenter med strukturlisteradtypen Produktion.</span><span class="sxs-lookup"><span data-stu-id="e2dec-114">The specified calculation quantity represents the costing lot size for the specified item, and for manufactured components that have a BOM line type of production.</span></span> <span data-ttu-id="e2dec-115">Detta beror på förutsättningen att komponenten kommer att produceras i exakt kvantitet.</span><span class="sxs-lookup"><span data-stu-id="e2dec-115">This is because it is assumed that the component will be produced to the exact quantity.</span></span> <span data-ttu-id="e2dec-116">Den kostnadskalkylerade partistorleken för andra tillverkade komponenter med strukturlisteradtypen Artikel avspeglar deras standardorderkvantitet.</span><span class="sxs-lookup"><span data-stu-id="e2dec-116">The costing lot size for other manufactured components that have a BOM line type of item will reflect their standard order quantity.</span></span>
-   <span data-ttu-id="e2dec-117">Specificerad beräkningskvantitet i en artikels strukturlisteberäkning vid tillverkning mot order − den specificerade beräkningskvantiteten fungerar som den kostnadskalkylerade partistorleken för artikeln och dess tillverkade komponenter när nedbrytningsläget Tillverka mot order används för strukturlisteberäkningar.</span><span class="sxs-lookup"><span data-stu-id="e2dec-117">Specified make-to-order calculation quantity in an item’s BOM calculation − The specified calculation quantity acts as the costing lot size for the item and its manufactured components when BOM calculations use a make-to-order explosion mode.</span></span> <span data-ttu-id="e2dec-118">Förutsättningen är att de tillverkade komponenterna produceras i exakt kvantitet, precis som en tillverkade komponent med strukturlisteradtypen Produktion.</span><span class="sxs-lookup"><span data-stu-id="e2dec-118">It is assumed that the manufactured components will be produced to the exact quantity, just like a manufactured component that has a BOM line type of production.</span></span>
-   <span data-ttu-id="e2dec-119">Angiven beräkningskvantitet i en orderspecifik strukturlisteberäkning − en orderspecifik strukturlisteberäkning kan utföras för en radartikel på en försäljningsorder, försäljningsoffert eller serviceorder.</span><span class="sxs-lookup"><span data-stu-id="e2dec-119">Specified calculation quantity in an order-specific BOM calculation − An order-specific BOM calculation can be performed for a line item on a sales order, sales quotation, or service order.</span></span> <span data-ttu-id="e2dec-120">Den angivna beräkningskvantiteten använder kvantiteten för den ursprungliga radartikeln, men standardkvantiteten kan ändras.</span><span class="sxs-lookup"><span data-stu-id="e2dec-120">The specified calculation quantity uses the quantity on the originating line item, but the default quantity can be overridden.</span></span> <span data-ttu-id="e2dec-121">Du kan välja om nedbrytningsläget Tillverka mot order eller Flera nivåer ska användas för den orderspecifika strukturlisteberäkningen.</span><span class="sxs-lookup"><span data-stu-id="e2dec-121">You can select whether the order-specific BOM calculation uses a make-to-order or multilevel explosion mode.</span></span>

<span data-ttu-id="e2dec-122">Den beräknade mängden av en tillverkad artikels periodiserade konstanta kostnader kallas tillägg.</span><span class="sxs-lookup"><span data-stu-id="e2dec-122">The calculated amount of a manufactured item’s amortized constant costs is termed charges.</span></span>






