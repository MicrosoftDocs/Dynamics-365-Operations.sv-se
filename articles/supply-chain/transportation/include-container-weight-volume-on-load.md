---
title: "Inkludera behållarens vikt och volym vid lastning"
description: "Detta avsnitt beskriver hur du konfigurerar och tillämpar olika funktioner för att inkludera containervikt och -volym på olika laster."
author: pjacobse
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: pjacobse
ms.search.validFrom: 2017-09-20
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 4190b5cb05cccc3d762d8ad153ecbd467fa0a332
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="include-container-weight-and-volume-on-load"></a><span data-ttu-id="352ce-103">Inkludera behållarens vikt och volym vid lastning</span><span class="sxs-lookup"><span data-stu-id="352ce-103">Include container weight and volume on load</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="352ce-104">Funktionen för att inkludera containervikt och -volym på en last ger en tydlig uppfattning om totalvikt och totalvolym för containers och varor som ska ingå i en last.</span><span class="sxs-lookup"><span data-stu-id="352ce-104">The functionality for including the container weight and volume on a load gives a clear representation of the total weight and volume of containers and items that are going on a load.</span></span>

<span data-ttu-id="352ce-105">En last innehåller en enda leverans eller flera leveranser, och dessa leveranser innehåller specifika varor som tillhör en enda försäljningsorder eller flera försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="352ce-105">A load contains a single shipment or multiple shipments, and these shipments contain distinct items that belong to a single sales order or multiple sales orders.</span></span> <span data-ttu-id="352ce-106">Varorna förvaras i en container, och containrarna lastas på en last.</span><span class="sxs-lookup"><span data-stu-id="352ce-106">The items are stored inside a container, and containers are loaded on a load.</span></span> <span data-ttu-id="352ce-107">Varor utanför en container lan också ingå i en last.</span><span class="sxs-lookup"><span data-stu-id="352ce-107">Items that are outside a container can also be part of a load.</span></span> <span data-ttu-id="352ce-108">Baserat på dessa villkor beräknar systemet värden för vikt och volym på lasten, detta genom att bedöma vikt och volym för såväl container som varor.</span><span class="sxs-lookup"><span data-stu-id="352ce-108">Based on these conditions, the system calculates values for the weight and volume on the load by considering the weight and volume of both containers and items.</span></span>

<span data-ttu-id="352ce-109">Om beräknade värden inte är exakta kan du justera dem genom att ange faktiska värden för lastens vikt och volym.</span><span class="sxs-lookup"><span data-stu-id="352ce-109">If the calculated values aren’t precise, you can adjust them by entering the actual values for the weight and volume on the load.</span></span> <span data-ttu-id="352ce-110">Värden för vikt och volym används inom processerna för transporthantering.</span><span class="sxs-lookup"><span data-stu-id="352ce-110">The values for the weight and volume are used in transportation management processes.</span></span> <span data-ttu-id="352ce-111">Värdena används exempelvis i arbetsstationen för avgiftsvägar, där de hjälper till att definiera avgifter och väg för laster, och de används också för distributörer och inloggning av förare.</span><span class="sxs-lookup"><span data-stu-id="352ce-111">For example, the values are used in the rate route workbench, where they help define the rate and route for loads, and they are also used for transportation tenders and driver check-in.</span></span>

## <a name="where-it-applies"></a><span data-ttu-id="352ce-112">Tillämpning</span><span class="sxs-lookup"><span data-stu-id="352ce-112">Where it applies</span></span>

<span data-ttu-id="352ce-113">Funktionen för att inkludera containervikt och -volym på en last gäller i processer för transporthantering, exempelvis arbetsstationen för avgiftsväg, distributörer och inloggning av förare.</span><span class="sxs-lookup"><span data-stu-id="352ce-113">The functionality for including the container weight and volume on a load applies in transportation management processes, such as the rate route workbench, transportation tenders, and driver check-in.</span></span>

## <a name="how-it-is-set-up"></a><span data-ttu-id="352ce-114">Inställningar</span><span class="sxs-lookup"><span data-stu-id="352ce-114">How it is set up</span></span>

<span data-ttu-id="352ce-115">Antalet containrar som bör övervägas för en last beräknas baserat på containerns vikt och volym, samt på den procentandel av containern som används.</span><span class="sxs-lookup"><span data-stu-id="352ce-115">The number of containers that should be considered for a load is calculated based on the weight and volume of the container, and on the percentage of the container is used.</span></span>

-   <span data-ttu-id="352ce-116">Klicka på **Lagerhantering** \> **Inställningar** \> **Container** \> **Containertyper** om du vill ange vikt och volym för en container.</span><span class="sxs-lookup"><span data-stu-id="352ce-116">To set the weight and volume for a container, click **Warehouse management** \> **Setup** \> **Containers** \> **Container types**.</span></span>

-   <span data-ttu-id="352ce-117">Klicka på **Lagerhantering** \> **Inställningar** \> **Containrar** \> **Behållargrupper** och ange sedan ett värde i fältet **Nyttjandedel av behållare i procent** om du vill ange nyttjandeandelen för en behållare.</span><span class="sxs-lookup"><span data-stu-id="352ce-117">To set the container utilization percentage, click **Warehouse management** \> **Setup** \> **Containers** \> **Container groups**, and then enter a value in the **Container utilization percentage** field.</span></span>

