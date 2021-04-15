---
title: Lagerplatser
description: Lagerplatser används med grundläggande lagerstyrning (Lagerstyrningssystem I) för att bestämma var artiklar lagras och var artiklar plockas i ett Lagerstyrningssystem I-lagerställe.
author: perlynne
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WMSLocation, WMSBlockingCause, WHSLocation
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2134
ms.assetid: 69bf6922-4151-447f-b678-4ba95637f54c
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4afbb4847a2d3175585ed270d8ecd8aac33c4b14
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5813133"
---
# <a name="inventory-locations"></a><span data-ttu-id="28e4f-103">Lagerplatser</span><span class="sxs-lookup"><span data-stu-id="28e4f-103">Inventory locations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="28e4f-104">Lagerplatser används med grundläggande lagerstyrning (Lagerstyrningssystem I) för att bestämma var artiklar lagras och var artiklar plockas i ett Lagerstyrningssystem I-lagerställe.</span><span class="sxs-lookup"><span data-stu-id="28e4f-104">Inventory locations are used with basic warehousing (WMS I) to determine where items are stored and where items are picked from in a WMS I warehouse.</span></span>

<span data-ttu-id="28e4f-105">Det här ämnet gäller funktioner i modulen Lagerhantering.</span><span class="sxs-lookup"><span data-stu-id="28e4f-105">This topic applies to features in the Inventory management module.</span></span> <span data-ttu-id="28e4f-106">Den gäller inte funktioner i modulen Lagerstyrning.</span><span class="sxs-lookup"><span data-stu-id="28e4f-106">It does not apply to features in the Warehouse management module.</span></span>

<span data-ttu-id="28e4f-107">Termen plats hänvisar till det ställe som artiklar lagras och hämtas från.</span><span class="sxs-lookup"><span data-stu-id="28e4f-107">The term location refers to the place that items are stored and drawn from.</span></span>

<span data-ttu-id="28e4f-108">För varje plats kan stället där artikeln infogas också anges.</span><span class="sxs-lookup"><span data-stu-id="28e4f-108">For each location, the place where the item is inserted can also be specified.</span></span> <span data-ttu-id="28e4f-109">Som standard är de samma.</span><span class="sxs-lookup"><span data-stu-id="28e4f-109">By default, they are the same.</span></span> <span data-ttu-id="28e4f-110">Artiklar infogas och hämtas vanligtvis från samma sida om en plats, men inte alltid.</span><span class="sxs-lookup"><span data-stu-id="28e4f-110">Items are usually inserted and drawn from the same side of a location, but not always.</span></span> <span data-ttu-id="28e4f-111">Artiklar som lagras i lagringsställningar infogas till exempel från en gång och hämtas från en annan.</span><span class="sxs-lookup"><span data-stu-id="28e4f-111">For example, items that are stored in live storage racks are inserted from one aisle and drawn from another.</span></span> <span data-ttu-id="28e4f-112">Huvudinmatningen anges av ett platsnamn, som vanligtvis bestäms av dess koordinater: lagerställe, gång, ställning, hylla och binge.</span><span class="sxs-lookup"><span data-stu-id="28e4f-112">The main input is given by a location name, which is usually determined by its coordinates: warehouse, aisle, rack, shelf, and bin.</span></span> <span data-ttu-id="28e4f-113">Det här namnet eller ID:t kan anges manuellt eller genereras från platsens koordinater, till exempel 01-02-03-4 för gång 1, ställning 2, hylla 3, binge 4 på sidan Lagerplatser.</span><span class="sxs-lookup"><span data-stu-id="28e4f-113">This name or ID can be entered manually or generated from the location coordinates—for example, 01-02-03-4 for aisle 1, rack 2, shelf 3, bin 4 in the Inventory locations page.</span></span>
<span data-ttu-id="28e4f-114">Platsegenskaper</span><span class="sxs-lookup"><span data-stu-id="28e4f-114">Location properties</span></span>

<span data-ttu-id="28e4f-115">En plats har följande egenskaper:</span><span class="sxs-lookup"><span data-stu-id="28e4f-115">A location has the following characteristics:</span></span>
-   <span data-ttu-id="28e4f-116">Storlek (höjd, bredd, djup, och därigenom volym)</span><span class="sxs-lookup"><span data-stu-id="28e4f-116">Size (height, width, depth, and thereby volume)</span></span>
-   <span data-ttu-id="28e4f-117">Plats för lagerställe, gång, ställning, hylla och binge.</span><span class="sxs-lookup"><span data-stu-id="28e4f-117">Warehouse, aisle, rack, shelf, and bin position</span></span>
-   <span data-ttu-id="28e4f-118">Platstyp (bulkplats, plockplats, inlastningsplats, utlastningsplats, plats för produktionsinleverans, inspektionplats eller kanban-storlager)</span><span class="sxs-lookup"><span data-stu-id="28e4f-118">Location type (bulk location, picking location, inbound dock, outbound dock, production input location, inspection location, or kanban supermarket)</span></span>

<span data-ttu-id="28e4f-119">Kontrolltext kan användas i onlinesystem för att bekräfta att operatören har valt rätt plats för en viss artikel.</span><span class="sxs-lookup"><span data-stu-id="28e4f-119">Check text can be used in online systems to verify that the operator has selected the correct location for a specific item.</span></span> <span data-ttu-id="28e4f-120">Kontrolltexten kan skapas manuellt eller som standard.</span><span class="sxs-lookup"><span data-stu-id="28e4f-120">This check text can be created manually or by default.</span></span>

## <a name="sort-codes"></a><span data-ttu-id="28e4f-121">Sorteringskoder</span><span class="sxs-lookup"><span data-stu-id="28e4f-121">Sort codes</span></span>
<span data-ttu-id="28e4f-122">Använd sorteringskoder om du vill optimera hanteringen av plockrader, som beskriver den information som krävs för att plocka artiklar från lagret, inklusive plockordning.</span><span class="sxs-lookup"><span data-stu-id="28e4f-122">Use sort codes to optimize the handling of picking lines, which describe the information that is required for picking items from inventory, including the picking order.</span></span> <span data-ttu-id="28e4f-123">Sorteringskoder kan innehålla gång och andra koordinater eller tilldelas manuellt för platsen.</span><span class="sxs-lookup"><span data-stu-id="28e4f-123">Sort codes can be specified by the aisle and other coordinates, or assigned manually for the location.</span></span>

## <a name="blocked-locations"></a><span data-ttu-id="28e4f-124">Spärrade platser</span><span class="sxs-lookup"><span data-stu-id="28e4f-124">Blocked locations</span></span>
<span data-ttu-id="28e4f-125">Ibland kanske du vill ange att en plats är blockerad under en tid, exempelvis under en reparation.</span><span class="sxs-lookup"><span data-stu-id="28e4f-125">Occasionally, you might want to indicate that a location is blocked for a period of time, for example, to allow for repairs.</span></span> <span data-ttu-id="28e4f-126">Vid andra tillfällen kanske man vill ange blockering av endast in- eller utleverans.</span><span class="sxs-lookup"><span data-stu-id="28e4f-126">At other times, you may want to indicate blocking of only the input or only output.</span></span>

## <a name="tree-structure"></a><span data-ttu-id="28e4f-127">Trädstruktur</span><span class="sxs-lookup"><span data-stu-id="28e4f-127">Tree structure</span></span>

<span data-ttu-id="28e4f-128">På sidan Lagerplatser kan du visa lagerställelayouten i en trädstruktur baserad på koordinaterna för lagerplatser, i ett definierat bildskärmsformat.</span><span class="sxs-lookup"><span data-stu-id="28e4f-128">In the Inventory locations page, you can view the warehouse layout in a tree structure based on the coordinates of inventory locations, in a defined display format.</span></span>

## <a name="maintain-inventory-locations-via-the-warehouse-form"></a><span data-ttu-id="28e4f-129">Hantera lagerplatser via formuläret Lagerställe</span><span class="sxs-lookup"><span data-stu-id="28e4f-129">Maintain inventory locations via the warehouse form</span></span>

<span data-ttu-id="28e4f-130">Det går att kopiera platser från ett lagerställe till ett annat och skapa platser via en guide.</span><span class="sxs-lookup"><span data-stu-id="28e4f-130">It is possible to copy locations from one warehouse to another and to create locations via a wizard.</span></span> <span data-ttu-id="28e4f-131">Innan du kör guiden bör du se till att du har definierat standardplatsnamnen på sidan Lagerställe.</span><span class="sxs-lookup"><span data-stu-id="28e4f-131">Before you run the wizard you should make sure that you have defined the default location names on the Warehouse page.</span></span>



<a name="additional-resources"></a><span data-ttu-id="28e4f-132">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="28e4f-132">Additional resources</span></span>
--------

[<span data-ttu-id="28e4f-133">Skapa en ny layout för lagerställe</span><span class="sxs-lookup"><span data-stu-id="28e4f-133">Create a new warehouse layout</span></span>](tasks/create-new-warehouse-layout.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]