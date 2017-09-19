---
title: "Dimensioner för kostnadselement"
description: "Som en av kärnapelarna i kostnadsredovisning, används kostnadselementen för att kategorisera och spåra var kostnaderna flödar till."
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CAMDimension
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 223204
ms.assetid: 1eda0e62-760b-4737-9dfd-3c3c38d80c1a
ms.search.region: global
ms.author: yuyus
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: 9e13fc9fa7e51a1299ca8698f581de979b680a7b
ms.openlocfilehash: 00a09120116183785d96ed1e18c577d5430fa16b
ms.contentlocale: sv-se
ms.lasthandoff: 09/18/2017

---

# <a name="cost-element-dimensions"></a><span data-ttu-id="15f6b-103">Dimensioner för kostnadselement</span><span class="sxs-lookup"><span data-stu-id="15f6b-103">Cost element dimensions</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="15f6b-104">Som en av kärnapelarna i kostnadsredovisning, används kostnadselementen för att kategorisera och spåra var kostnaderna flödar till.</span><span class="sxs-lookup"><span data-stu-id="15f6b-104">As one of the core pillars in Cost accounting, cost element dimensions are used to categorize and track where costs flow to.</span></span> 

<span data-ttu-id="15f6b-105">Ett kostnadselement motsvarar en kostnadsrelevant artikel i kontoplanen.</span><span class="sxs-lookup"><span data-stu-id="15f6b-105">A cost element corresponds to a cost-relevant item in the chart of accounts.</span></span> <span data-ttu-id="15f6b-106">I princip kan det vara valfri typ av element på den lägsta nivån i en verksamhet som kostnader kan flöda till.</span><span class="sxs-lookup"><span data-stu-id="15f6b-106">Basically, it can be any type of element at the lowest level in a business where costs can flow to.</span></span> <span data-ttu-id="15f6b-107">Kostnadselement som ett begrepp sträcker sig från redovisningskonton till alla kostnadsrelevanta resurser.</span><span class="sxs-lookup"><span data-stu-id="15f6b-107">Cost elements as a concept range from ledger accounts to all cost-relevant resources.</span></span> <span data-ttu-id="15f6b-108">För närvarande stöder kostnadsredovisning huvudbokskonton.</span><span class="sxs-lookup"><span data-stu-id="15f6b-108">Currently, Cost accounting supports ledger accounts.</span></span>

## <a name="two-types-of-cost-elements"></a><span data-ttu-id="15f6b-109">Två typer av kostnadselement</span><span class="sxs-lookup"><span data-stu-id="15f6b-109">Two types of cost elements</span></span>
<span data-ttu-id="15f6b-110">Det finns två typer av kostnadselement: primära kostnadselement och sekundära kostnadselement.</span><span class="sxs-lookup"><span data-stu-id="15f6b-110">There are two types of cost elements: primary cost elements and secondary cost elements.</span></span> <span data-ttu-id="15f6b-111">Följande tabell beskriver skillnaden mellan de två typerna.</span><span class="sxs-lookup"><span data-stu-id="15f6b-111">The following table describes the difference between the two types.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><span data-ttu-id="15f6b-112"><strong>Primära kostnadselement</strong></span><span class="sxs-lookup"><span data-stu-id="15f6b-112"><strong>Primary cost elements</strong></span></span></td>
<td><span data-ttu-id="15f6b-113"><strong>Sekundära kostnadselement</strong></span><span class="sxs-lookup"><span data-stu-id="15f6b-113"><strong>Secondary cost elements</strong></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="15f6b-114">De primära kostnadselementen representerar flödet av kostnader från ekonomisk redovisning till kostnadsredovisning.</span><span class="sxs-lookup"><span data-stu-id="15f6b-114">The primary cost elements represent the flow of costs from financial accounting to cost accounting.</span></span> <span data-ttu-id="15f6b-115">Kostnadselementstrukturen motsvarar resultaträkningsstrukturen i huvudboken, där ett kostnadselement kan motsvara en huvudkonto.</span><span class="sxs-lookup"><span data-stu-id="15f6b-115">The cost element structure corresponds to the profit and loss account structure in the general ledger, where a cost element can correspond to a main account.</span></span> <span data-ttu-id="15f6b-116">Alla rubrikkontona kan inte nödvändigtvis representeras som kostnadselement beroende på företagets behov.</span><span class="sxs-lookup"><span data-stu-id="15f6b-116">Not all main accounts may necessarily be represented as cost elements depending on the business needs.</span></span> <span data-ttu-id="15f6b-117">Exempel på primära kostnadselement inkluderar:</span><span class="sxs-lookup"><span data-stu-id="15f6b-117">Examples of primary cost elements include:</span></span>
<ul>
<li><span data-ttu-id="15f6b-118">Kostnader för sålda varor (KSV)</span><span class="sxs-lookup"><span data-stu-id="15f6b-118">Costs of goods sold (COGs)</span></span></li>
<li><span data-ttu-id="15f6b-119">Indirekta materialkostnader</span><span class="sxs-lookup"><span data-stu-id="15f6b-119">Indirect material costs</span></span></li>
<li><span data-ttu-id="15f6b-120">Personalkostnader</span><span class="sxs-lookup"><span data-stu-id="15f6b-120">Personnel costs</span></span></li>
<li><span data-ttu-id="15f6b-121">Energikostnader</span><span class="sxs-lookup"><span data-stu-id="15f6b-121">Energy costs</span></span></li>
</ul></td>
<td><span data-ttu-id="15f6b-122">De sekundära kostnadselementen representerar flödet av kostnader internt eftersom dessa kostnader skapas och används bara i kostnadsredovisning.</span><span class="sxs-lookup"><span data-stu-id="15f6b-122">The secondary cost elements represent the flow of costs internally because these costs are created and used only in Cost accounting.</span></span> <span data-ttu-id="15f6b-123">De används för att säkerställa att kostnadskällan kan spåras.</span><span class="sxs-lookup"><span data-stu-id="15f6b-123">They are used to secure that the source of costs can be traced.</span></span> <span data-ttu-id="15f6b-124">Dessa kostnadelement används i kostnadsallokeringar och beräkningar av indirekta kostnader.</span><span class="sxs-lookup"><span data-stu-id="15f6b-124">These cost elements are used in cost allocations and overhead calculations.</span></span> <span data-ttu-id="15f6b-125">Exempel på sekundära kostnadselement inkluderar:</span><span class="sxs-lookup"><span data-stu-id="15f6b-125">Examples of secondary cost elements include:</span></span>
<ul>
<li><span data-ttu-id="15f6b-126">Tillverkningskostnader</span><span class="sxs-lookup"><span data-stu-id="15f6b-126">Production costs</span></span></li>
<li><span data-ttu-id="15f6b-127">Tillverknings-, material- och marknadsföringsomkostnader</span><span class="sxs-lookup"><span data-stu-id="15f6b-127">Production, material, and marketing overheads</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="cost-element-dimensions-and-cost-element-dimension-members"></a><span data-ttu-id="15f6b-128">Kostnadselement och+ dimensionsmedlemmar för kostnadselement.</span><span class="sxs-lookup"><span data-stu-id="15f6b-128">Cost element dimensions and cost element dimension members</span></span>
<span data-ttu-id="15f6b-129">Kostnadselement kallas *kostnadselementdimensioner*.</span><span class="sxs-lookup"><span data-stu-id="15f6b-129">Cost elements are referred to as *cost element dimensions* .</span></span> <span data-ttu-id="15f6b-130">De enskilda dimensionsvärdena kallas *dimensionsmedlemmar för kostnadselement*.</span><span class="sxs-lookup"><span data-stu-id="15f6b-130">The individual dimension values are called *cost element dimension members*.</span></span> <span data-ttu-id="15f6b-131">Du kan till exempel ha en amerikansk kontoplanstruktur (COA) som utgör grunden för din lagstadgade rapportering.</span><span class="sxs-lookup"><span data-stu-id="15f6b-131">For example, you have a US chart of accounts structure (COA) that is the base for your statutory reporting.</span></span> <span data-ttu-id="15f6b-132">Detta COA används som kostnadselementdimension.</span><span class="sxs-lookup"><span data-stu-id="15f6b-132">This COA is used as the cost element dimension.</span></span> <span data-ttu-id="15f6b-133">Kontona som är primära kostnadselement, representeras som dimensionsmedlemmar för kostnadselement i kostnadsredovisning.</span><span class="sxs-lookup"><span data-stu-id="15f6b-133">The accounts, which are primary cost elements, are represented as the cost element dimension members in Cost accounting.</span></span> <span data-ttu-id="15f6b-134">Följande exempel visar en skärmdump av huvudkonton som kostnadselementdimensionen med dess faktiska huvudkonton som dimensionsmedlem för kostnadselement.</span><span class="sxs-lookup"><span data-stu-id="15f6b-134">The following screenshot shows an example of Main Accounts as the cost element dimension with its actual main accounts as the cost element dimension members.</span></span> 

<span data-ttu-id="15f6b-135">[![dimensioner-för-kostnadselement](./media/cost-element-dimensions.png)](./media/cost-element-dimensions.png)</span><span class="sxs-lookup"><span data-stu-id="15f6b-135">[![cost-element-dimensions](./media/cost-element-dimensions.png)](./media/cost-element-dimensions.png)</span></span>

## <a name="import-cost-element-dimension-members-through-data-connectors"></a><span data-ttu-id="15f6b-136">Importera dimensionsmedlemmar för kostnadselement via datakopplingar</span><span class="sxs-lookup"><span data-stu-id="15f6b-136">Import cost element dimension members through data connectors</span></span>
<span data-ttu-id="15f6b-137">För att underlätta inställningarna av dimensionsmedlemmar för kostnadselement i kostnadsredovisning kan du använda datakopplingar, som antingen är föruppbyggda eller personligt anpassade för att hämta de primära kostnadselementen från ett eller flera källsystem.</span><span class="sxs-lookup"><span data-stu-id="15f6b-137">To ease the setup of cost element dimension members in Cost accounting, you can use data connectors that are either pre-built or your custom build to retrieve the primary cost elements from one or more source systems.</span></span>

## <a name="implementation-considerations"></a><span data-ttu-id="15f6b-138">Implementeringöverväganden</span><span class="sxs-lookup"><span data-stu-id="15f6b-138">Implementation considerations</span></span>
<span data-ttu-id="15f6b-139">Eftersom kostnadselement representerar den lägsta nivån i kostnadsdetaljer, ska du se till att alla kostnadselement som är nödvändiga för att göra chefs rapporteringen inkluderas när du implementerar kostnadselementstrukturen.</span><span class="sxs-lookup"><span data-stu-id="15f6b-139">As cost elements represent the lowest level of cost details, you should make sure that all the cost elements required to make the managerial reporting are included when you implement the cost elements structure.</span></span> <span data-ttu-id="15f6b-140">Det kan vara en utmaning att hitta ett lämpligt antal kostnadselement för kostnadskontroll.</span><span class="sxs-lookup"><span data-stu-id="15f6b-140">It can be a challenge to find an appropriate number of cost elements for cost control.</span></span> <span data-ttu-id="15f6b-141">Att ha tusentals kostnadselement kan göra det svårt att kontrollera varje kostnadselement.</span><span class="sxs-lookup"><span data-stu-id="15f6b-141">Having thousands of cost elements can make it difficult to control each cost element.</span></span> <span data-ttu-id="15f6b-142">Alternativt kan du gruppera kostnadselement och hantera kostnadskontroll på en samlad nivå.</span><span class="sxs-lookup"><span data-stu-id="15f6b-142">As an alternative, you can group cost elements and manage cost control at an aggregated level.</span></span>




