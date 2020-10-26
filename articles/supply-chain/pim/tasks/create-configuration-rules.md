---
title: Skapa konfigurationsregler
description: Den här proceduren skapar konfigurationsregler som kan användas för dimensionsbaserad konfiguration för att framtvinga eller förhindra vissa kombinationer av strukturlisterader.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BOMTable, BOMConfigRule, ConfigItemIdLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6bc0af4d95e9430d0b5c8b7fc9a4ade076802044
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/10/2020
ms.locfileid: "3986273"
---
# <a name="create-configuration-rules"></a><span data-ttu-id="55c8b-103">Skapa konfigurationsregler</span><span class="sxs-lookup"><span data-stu-id="55c8b-103">Create configuration rules</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="55c8b-104">Den här proceduren skapar konfigurationsregler som kan användas för dimensionsbaserad konfiguration för att framtvinga eller förhindra vissa kombinationer av strukturlisterader.</span><span class="sxs-lookup"><span data-stu-id="55c8b-104">This procedure creates configuration rules that can be used for dimension-based configuration to enforce or prevent certain combinations of BOM lines.</span></span> <span data-ttu-id="55c8b-105">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="55c8b-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="55c8b-106">Detta är den första proceduren utav sju som förklarar hur du ställer upp kombinationer för dimensionsbaserad konfiguration.</span><span class="sxs-lookup"><span data-stu-id="55c8b-106">This is the seventh procedure out of eight that explains how to build combinations for dimension-based configuration.</span></span>

1. <span data-ttu-id="55c8b-107">Gå till Produktinformationshantering > Strukturlistor och formler > Strukturlistor.</span><span class="sxs-lookup"><span data-stu-id="55c8b-107">Go to Product information management > Bills of materials and formulas > Bills of materials.</span></span>
2. <span data-ttu-id="55c8b-108">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="55c8b-108">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="55c8b-109">Hitta och välj strukturlistan för den dimensionsbaserade konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="55c8b-109">Find and select the BOM for the dimension-based configuration.</span></span>  
3. <span data-ttu-id="55c8b-110">Klicka på Alternativ i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="55c8b-110">On the Action Pane, click Options.</span></span>
4. <span data-ttu-id="55c8b-111">Klicka på Ändra vy.</span><span class="sxs-lookup"><span data-stu-id="55c8b-111">Click Change view.</span></span>
5. <span data-ttu-id="55c8b-112">Klicka på Huvudvy.</span><span class="sxs-lookup"><span data-stu-id="55c8b-112">Click Header view.</span></span>
    * <span data-ttu-id="55c8b-113">Öppna huvudvyn för åtkomst till snabbfliken Konfigurationsflöde.</span><span class="sxs-lookup"><span data-stu-id="55c8b-113">Open the header view to access the Configuration route FastTab.</span></span>  
6. <span data-ttu-id="55c8b-114">Visa eller dölj avsnittet Konfigureringsflöde.</span><span class="sxs-lookup"><span data-stu-id="55c8b-114">Expand or collapse the Configuration route section.</span></span>
    * <span data-ttu-id="55c8b-115">Snabbfliken Konfigurationsflöde måste vara i det expanderade läget.</span><span class="sxs-lookup"><span data-stu-id="55c8b-115">The Configuration route FastTab must be in the expanded mode.</span></span>  
7. <span data-ttu-id="55c8b-116">Klicka på konfigurationsregler.</span><span class="sxs-lookup"><span data-stu-id="55c8b-116">Click Configuration rules.</span></span>
8. <span data-ttu-id="55c8b-117">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="55c8b-117">Click New.</span></span>
9. <span data-ttu-id="55c8b-118">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="55c8b-118">In the list, mark the selected row.</span></span>
10. <span data-ttu-id="55c8b-119">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="55c8b-119">In the Item number field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="55c8b-120">Artiklarna i den aktuella konfigurationsgruppen visas.</span><span class="sxs-lookup"><span data-stu-id="55c8b-120">The items in the current configuration group are displayed.</span></span> <span data-ttu-id="55c8b-121">Välj den som representerar villkoret i regeln.</span><span class="sxs-lookup"><span data-stu-id="55c8b-121">Select the one that represents the condition in the rule.</span></span>  
11. <span data-ttu-id="55c8b-122">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="55c8b-122">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="55c8b-123">Markera ett alternativ i fältet Metod.</span><span class="sxs-lookup"><span data-stu-id="55c8b-123">In the Method field, select an option.</span></span>
    * <span data-ttu-id="55c8b-124">Det går att framtvinga antingen en markering eller en avmarkering av en artikel från en annan konfigurationsgrupp.</span><span class="sxs-lookup"><span data-stu-id="55c8b-124">It is possible to enforce either a selection or a deselection of an item from another configuration group.</span></span>  
13. <span data-ttu-id="55c8b-125">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Härledd grupp.</span><span class="sxs-lookup"><span data-stu-id="55c8b-125">In the Derived group field, click the drop-down button to open the lookup.</span></span>
14. <span data-ttu-id="55c8b-126">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="55c8b-126">In the list, find and select the desired record.</span></span>
15. <span data-ttu-id="55c8b-127">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="55c8b-127">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="55c8b-128">Markera den valda konfigurationsgruppen.</span><span class="sxs-lookup"><span data-stu-id="55c8b-128">Select the desired configuration group.</span></span>  
16. <span data-ttu-id="55c8b-129">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Härlett artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="55c8b-129">In the Derived item number field, click the drop-down button to open the lookup.</span></span>
17. <span data-ttu-id="55c8b-130">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="55c8b-130">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="55c8b-131">Välj det artikelnummer som ska markeras eller avmarkeras beroende på vilken metod som har valts.</span><span class="sxs-lookup"><span data-stu-id="55c8b-131">Select the item number that will be either selected or deselected depending on the chosen method.</span></span>  
18. <span data-ttu-id="55c8b-132">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="55c8b-132">Close the page.</span></span>

