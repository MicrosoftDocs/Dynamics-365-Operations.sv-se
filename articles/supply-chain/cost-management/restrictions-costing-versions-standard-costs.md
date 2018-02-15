---
title: "Begränsningar för kostnadsversioner av standardkostnader"
description: "Det här avsnittet beskriver de restriktioner som gäller för kostnadsversioner av standardkostnader."
author: AndersGirke
manager: AnnBe
ms.date: 01/17/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CostingVersion
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: e14d5d11e987d2dbc841f86c39fc7e94864144d3
ms.openlocfilehash: 658575492597eed91509561f4710f07e271c53c8
ms.contentlocale: sv-se
ms.lasthandoff: 01/17/2018

---


#  <a name="restrictions-on-costing-versions-for-standard-costs"></a><span data-ttu-id="55023-103">Begränsningar för kostnadsversioner av standardkostnader</span><span class="sxs-lookup"><span data-stu-id="55023-103">Restrictions on costing versions for standard costs</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="55023-104">Det här avsnittet beskriver de restriktioner som gäller för kostnadsversioner av standardkostnader.</span><span class="sxs-lookup"><span data-stu-id="55023-104">This topic describes the restrictions that apply to a costing version for standard costs.</span></span> 

<span data-ttu-id="55023-105">Följande restriktionerna ser till att standardkostnadsprinciperna efterlevs:</span><span class="sxs-lookup"><span data-stu-id="55023-105">The following restrictions help guarantee adherence to standard costing principles:</span></span>

-  <span data-ttu-id="55023-106">Avgifter måste inkluderas i en artikels kostnad.</span><span class="sxs-lookup"><span data-stu-id="55023-106">Charges must be included in an item's cost.</span></span> <span data-ttu-id="55023-107">Avgifterna för en tillverkad artikel representerar de amorterade konstanta kostnaderna i strukturliste- och flödesinformationen.</span><span class="sxs-lookup"><span data-stu-id="55023-107">The charges for a manufactured item represent the amortized constant costs in the bill of materials (BOM) and route information.</span></span> <span data-ttu-id="55023-108">Avgifterna måste därför inkluderas i enhetskostnaden.</span><span class="sxs-lookup"><span data-stu-id="55023-108">Therefore, the charges must be included in the unit cost.</span></span> <span data-ttu-id="55023-109">Avgifterna för en inköpt artikel ska också inkluderas i artikelns enhetskostnad.</span><span class="sxs-lookup"><span data-stu-id="55023-109">The charges for a purchased item are also included in the item's unit cost.</span></span>

-  <span data-ttu-id="55023-110">Beräkningen av standardkostnader för tillverkade artiklar måste baseras på kostnadsposterna i en kostnadsversion för standardkostnader.</span><span class="sxs-lookup"><span data-stu-id="55023-110">Calculation of standard costs for manufactured items must be based on the cost records in a costing version for standard costs.</span></span> <span data-ttu-id="55023-111">Alternativa källor till kostnadsdata kan bara användas med en kostnadsversion för planerade kostnader, till exempel handelsavtal för inköpspris för inköpta artiklar.</span><span class="sxs-lookup"><span data-stu-id="55023-111">Alternative sources of cost data can be used only with a costing version for planned costs, such as purchase price trade agreements for purchased items.</span></span> <span data-ttu-id="55023-112">Alternativa källor till kostnadsdata definieras av strukturlisteberäkningsgruppen.</span><span class="sxs-lookup"><span data-stu-id="55023-112">Alternative sources of cost data are defined by the BOM calculation group.</span></span>

-  <span data-ttu-id="55023-113">Strukturlisteberäkningar måste utföras i ett läge med en enda nivå.</span><span class="sxs-lookup"><span data-stu-id="55023-113">BOM calculations must be performed in a single-level explosion mode.</span></span>

<span data-ttu-id="55023-114">Artikelkostnadsdata för standardkostnader kan kopieras till en annan kostnadsversion som innehåller standardkostnader eller planerade kostnader.</span><span class="sxs-lookup"><span data-stu-id="55023-114">The item cost data for standard costs can be copied to another costing version that contains standard costs or planned costs.</span></span> <span data-ttu-id="55023-115">Artikelkostnadsdata för planerade kostnader kan emellertid inte kopieras till en kostnadsversion som innehåller standardkostnader, eftersom restriktionerna som beskrivits tidigare i det här avsnittet inte gäller för planerade kostnader.</span><span class="sxs-lookup"><span data-stu-id="55023-115">However, the item cost data for planned costs can't be copied to a cost version that contains standard costs, because the restrictions that are listed earlier in this topic don't apply to planned costs.</span></span>

<a name="related-topics"></a><span data-ttu-id="55023-116">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="55023-116">Related topics</span></span>
--------

[<span data-ttu-id="55023-117">Kostnadsversioner</span><span class="sxs-lookup"><span data-stu-id="55023-117">Costing versions</span></span>](costing-versions.md)

[<span data-ttu-id="55023-118">Uppdatering av standardkostnader i en icke-tillverkningsmiljö</span><span class="sxs-lookup"><span data-stu-id="55023-118">Update standard costs in a non-manufacturing environment</span></span>](update-standard-costs-non-manufacturing-environment.md)

[<span data-ttu-id="55023-119">Förbereda underhåll av standardkostnader för tillverkade artiklar</span><span class="sxs-lookup"><span data-stu-id="55023-119">Prepare to maintain standard costs for manufactured items</span></span>](update-standard-costs-manufacturing-environment.md)


