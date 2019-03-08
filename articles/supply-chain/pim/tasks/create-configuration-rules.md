---
title: Skapa konfigurationsregler
description: Den här proceduren skapar konfigurationsregler som kan användas för dimensionsbaserad konfiguration för att framtvinga eller förhindra vissa kombinationer av strukturlisterader.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BOMTable, BOMConfigRule, ConfigItemIdLookup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a315ddecd2e10f508b86ac8ea18a36df71616963
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "314749"
---
# <a name="create-configuration-rules"></a><span data-ttu-id="2e345-103">Skapa konfigurationsregler</span><span class="sxs-lookup"><span data-stu-id="2e345-103">Create configuration rules</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="2e345-104">Den här proceduren skapar konfigurationsregler som kan användas för dimensionsbaserad konfiguration för att framtvinga eller förhindra vissa kombinationer av strukturlisterader.</span><span class="sxs-lookup"><span data-stu-id="2e345-104">This procedure creates configuration rules that can be used for dimension-based configuration to enforce or prevent certain combinations of BOM lines.</span></span> <span data-ttu-id="2e345-105">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="2e345-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="2e345-106">Detta är den första proceduren utav sju som förklarar hur du ställer upp kombinationer för dimensionsbaserad konfiguration.</span><span class="sxs-lookup"><span data-stu-id="2e345-106">This is the seventh procedure out of eight that explains how to build combinations for dimension-based configuration.</span></span>

1. <span data-ttu-id="2e345-107">Gå till Produktinformationshantering > Strukturlistor och formler > Strukturlistor.</span><span class="sxs-lookup"><span data-stu-id="2e345-107">Go to Product information management > Bills of materials and formulas > Bills of materials.</span></span>
2. <span data-ttu-id="2e345-108">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="2e345-108">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="2e345-109">Hitta och välj strukturlistan för den dimensionsbaserade konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="2e345-109">Find and select the BOM for the dimension-based configuration.</span></span>  
3. <span data-ttu-id="2e345-110">Klicka på Alternativ i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="2e345-110">On the Action Pane, click Options.</span></span>
4. <span data-ttu-id="2e345-111">Klicka på Ändra vy.</span><span class="sxs-lookup"><span data-stu-id="2e345-111">Click Change view.</span></span>
5. <span data-ttu-id="2e345-112">Klicka på Huvudvy.</span><span class="sxs-lookup"><span data-stu-id="2e345-112">Click Header view.</span></span>
    * <span data-ttu-id="2e345-113">Öppna huvudvyn för åtkomst till snabbfliken Konfigurationsflöde.</span><span class="sxs-lookup"><span data-stu-id="2e345-113">Open the header view to access the Configuration route FastTab.</span></span>  
6. <span data-ttu-id="2e345-114">Visa eller dölj avsnittet Konfigureringsflöde.</span><span class="sxs-lookup"><span data-stu-id="2e345-114">Expand or collapse the Configuration route section.</span></span>
    * <span data-ttu-id="2e345-115">Snabbfliken Konfigurationsflöde måste vara i det expanderade läget.</span><span class="sxs-lookup"><span data-stu-id="2e345-115">The Configuration route FastTab must be in the expanded mode.</span></span>  
7. <span data-ttu-id="2e345-116">Klicka på konfigurationsregler.</span><span class="sxs-lookup"><span data-stu-id="2e345-116">Click Configuration rules.</span></span>
8. <span data-ttu-id="2e345-117">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="2e345-117">Click New.</span></span>
9. <span data-ttu-id="2e345-118">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="2e345-118">In the list, mark the selected row.</span></span>
10. <span data-ttu-id="2e345-119">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="2e345-119">In the Item number field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="2e345-120">Artiklarna i den aktuella konfigurationsgruppen visas.</span><span class="sxs-lookup"><span data-stu-id="2e345-120">The items in the current configuration group are displayed.</span></span> <span data-ttu-id="2e345-121">Välj den som representerar villkoret i regeln.</span><span class="sxs-lookup"><span data-stu-id="2e345-121">Select the one that represents the condition in the rule.</span></span>  
11. <span data-ttu-id="2e345-122">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="2e345-122">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="2e345-123">Markera ett alternativ i fältet Metod.</span><span class="sxs-lookup"><span data-stu-id="2e345-123">In the Method field, select an option.</span></span>
    * <span data-ttu-id="2e345-124">Det går att framtvinga antingen en markering eller en avmarkering av en artikel från en annan konfigurationsgrupp.</span><span class="sxs-lookup"><span data-stu-id="2e345-124">It is possible to enforce either a selection or a deselection of an item from another configuration group.</span></span>  
13. <span data-ttu-id="2e345-125">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Härledd grupp.</span><span class="sxs-lookup"><span data-stu-id="2e345-125">In the Derived group field, click the drop-down button to open the lookup.</span></span>
14. <span data-ttu-id="2e345-126">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="2e345-126">In the list, find and select the desired record.</span></span>
15. <span data-ttu-id="2e345-127">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="2e345-127">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="2e345-128">Markera den valda konfigurationsgruppen.</span><span class="sxs-lookup"><span data-stu-id="2e345-128">Select the desired configuration group.</span></span>  
16. <span data-ttu-id="2e345-129">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Härlett artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="2e345-129">In the Derived item number field, click the drop-down button to open the lookup.</span></span>
17. <span data-ttu-id="2e345-130">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="2e345-130">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="2e345-131">Välj det artikelnummer som ska markeras eller avmarkeras beroende på vilken metod som har valts.</span><span class="sxs-lookup"><span data-stu-id="2e345-131">Select the item number that will be either selected or deselected depending on the chosen method.</span></span>  
18. <span data-ttu-id="2e345-132">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="2e345-132">Close the page.</span></span>

