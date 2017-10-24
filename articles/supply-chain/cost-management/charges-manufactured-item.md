---
title: "Visa avgifter för en tillverkad artikel"
description: "En tillverkad artikels konstanta kostnader återspeglar driftställtiderna och komponenterna med en konstant kvantitet eller ett konstant kassationsbelopp."
author: AndersGirke
manager: AnnBe
ms.date: 04/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CostingVersion, InventItemPrice
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 274483
ms.assetid: 6f5b851b-c5a7-43ef-b380-0d316667c1ef
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.dyn365.ops.intro: AX 7.0.0
ms.search.validFrom: 2016-02-28
ms.translationtype: HT
ms.sourcegitcommit: a61761a5c9d98befd67682e1790af5377b7a55e1
ms.openlocfilehash: f0ce01b21f62ee91c861b45e92f87b95be0476de
ms.contentlocale: sv-se
ms.lasthandoff: 10/13/2017

---

# <a name="display-charges-for-a-manufactured-item"></a><span data-ttu-id="11d1b-103">Visa avgifter för en tillverkad artikel</span><span class="sxs-lookup"><span data-stu-id="11d1b-103">Display charges for a manufactured item</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="11d1b-104">En tillverkad artikels konstanta kostnader återspeglar driftställtiderna och komponenterna med en konstant kvantitet eller ett konstant kassationsbelopp.</span><span class="sxs-lookup"><span data-stu-id="11d1b-104">The constant costs of a manufactured item reflect the operation setup times and the components that have a constant quantity or a constant scrap amount.</span></span>

<span data-ttu-id="11d1b-105">Det beräknade beloppet för en artikels kostnader kan visas med artikelns enhetskostnad.</span><span class="sxs-lookup"><span data-stu-id="11d1b-105">The calculated amount of an item's charges can be displayed with the item's unit costs.</span></span> <span data-ttu-id="11d1b-106">Tilläggen visas emellertid ibland som separata fält, och de inkluderas inte i artikelns enhetskostnad.</span><span class="sxs-lookup"><span data-stu-id="11d1b-106">However, the charges are sometimes displayed as separate fields, and they are not included in the item's unit costs.</span></span> <span data-ttu-id="11d1b-107">När avgifterna visas som separata fält, visar ett fält det totala avgiftsbeloppet och andra fält visar kostnadspartistorleken som används för att amortera beloppet.</span><span class="sxs-lookup"><span data-stu-id="11d1b-107">When the charges appear as separate fields, one field displays the total amount of charges, and another field displays the costing lot size that is used to amortize the amount.</span></span> <span data-ttu-id="11d1b-108">T.ex. sidan Artikelpris visar avgifterna som två separata fält.</span><span class="sxs-lookup"><span data-stu-id="11d1b-108">The Item price page, for example, displays the charges as two separate fields.</span></span> <span data-ttu-id="11d1b-109">Emellertid visar sidan Slutförd artikelns totala kostnad per enhet och de amorterade kostnaderna ingår i enhetskostnaderna.</span><span class="sxs-lookup"><span data-stu-id="11d1b-109">However, the Complete page displays the item's total cost per unit, and the amortized costs are included in the unit costs.</span></span>

<span data-ttu-id="11d1b-110">Avgifterna för en tillverkad artikel inkluderas alltid i artikelns enhetskostnad i standardkostnadssyfte.</span><span class="sxs-lookup"><span data-stu-id="11d1b-110">The charges for a manufactured item are always included in the item's unit cost for standard cost purposes.</span></span> <span data-ttu-id="11d1b-111">De kan valfritt inkluderas för planerade kostnader.</span><span class="sxs-lookup"><span data-stu-id="11d1b-111">They can optionally be included for planned cost purposes.</span></span> <span data-ttu-id="11d1b-112">En policy i kostnadsversionen gör det möjligt att inkludera avgifter i kostnaden för en tillverkad artikel.</span><span class="sxs-lookup"><span data-stu-id="11d1b-112">A policy in the costing version enforces the inclusion of charges in the cost of a manufactured item.</span></span> <span data-ttu-id="11d1b-113">När du aktiverar en artikels kostnadspost uppdaterar du avgifterna för artikels baskostnadsinformation, vilket visas på sidan Artikelpris.</span><span class="sxs-lookup"><span data-stu-id="11d1b-113">When you activate an item's cost record, you update the charges for the item's base cost information, which is displayed in the Item price page.</span></span> <span data-ttu-id="11d1b-114">Avgifterna visas ibland som två separata fält, och de inkluderas inte i artikelns enhetskostnad.</span><span class="sxs-lookup"><span data-stu-id="11d1b-114">The charges are displayed as two separate fields, and they are not included in the item's unit cost.</span></span> <span data-ttu-id="11d1b-115">Varje aktivering uppdaterar artikelns baskostnadsinformation, även om aktiveringen återspeglar olika siter.</span><span class="sxs-lookup"><span data-stu-id="11d1b-115">Each activation updates the item's base cost information, even if the activation reflects different sites.</span></span> <span data-ttu-id="11d1b-116">Därför bör du visa baskostnadsinformation som referensinformation.</span><span class="sxs-lookup"><span data-stu-id="11d1b-116">Therefore, you should view the base cost information as reference information.</span></span>






