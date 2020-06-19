---
title: Kostnadsberäkningsnivå
description: I det här avsnittet beskrivs den strukturlistenivå som har namnet kostnadsberäkningsnivå. Denna strukturlistenivå omfattar inte produktions- och batchorder från beräkningar.
author: AndersGirke
manager: tfehr
ms.date: 04/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2020-04-23
ms.dyn365.ops.version: Release 10.0.12
ms.openlocfilehash: 52b77e794ee38add556ac01d62c973b38c48a548
ms.sourcegitcommit: a3cd2783ae120ac6681431c010b9b126a9ca7d94
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/29/2020
ms.locfileid: "3410984"
---
# <a name="cost-calculation-level"></a><span data-ttu-id="dff04-104">Kostnadsberäkningsnivå</span><span class="sxs-lookup"><span data-stu-id="dff04-104">Cost calculation level</span></span>

<span data-ttu-id="dff04-105">Den strukturlistenivå som har den namngivna **kostnadsberäknings nivån** utesluter produktionsorder och batchorder från sina beräkningar.</span><span class="sxs-lookup"><span data-stu-id="dff04-105">The bill of materials (BOM) level that is named **Cost calculation level** excludes production orders and batch orders from its calculations.</span></span> <span data-ttu-id="dff04-106">Systemet använder den här nivån när kostnadsberäkningar i kostnadsversioner körs.</span><span class="sxs-lookup"><span data-stu-id="dff04-106">The system uses this level when it runs cost calculations in costing versions.</span></span> <span data-ttu-id="dff04-107">I processer som omberäkningar och lagerstängningar använder systemet strukturlistenivån **Kostnadsnivå** i stället.</span><span class="sxs-lookup"><span data-stu-id="dff04-107">In processes such as recalculation and inventory close, the system uses the **Costing level** BOM level instead.</span></span>

<span data-ttu-id="dff04-108">Följande enkla scenario visar skillnaderna mellan **kostnadsberäkningsnivån** och strukturnivån på **kostnadsnivån**.</span><span class="sxs-lookup"><span data-stu-id="dff04-108">The following simple scenario shows the differences between the **Cost calculation level** BOM level and the **Costing level** BOM level.</span></span>

<span data-ttu-id="dff04-109">Du har tre produkter: A, B och C. Produkt C är komponenten av produkt B och produkt B är komponenten av produkt A.</span><span class="sxs-lookup"><span data-stu-id="dff04-109">You have three products: A, B, and C. Product C is the component of product B, and product B is the component of product A.</span></span>

- <span data-ttu-id="dff04-110">**Kostnadsnivån** tilldelas följande strukturlistenivåer:</span><span class="sxs-lookup"><span data-stu-id="dff04-110">**Costing level** assigns the following BOM levels:</span></span>

    - <span data-ttu-id="dff04-111">**Produkt A:** 0</span><span class="sxs-lookup"><span data-stu-id="dff04-111">**Product A:** 0</span></span>
    - <span data-ttu-id="dff04-112">**Produkt B:** 1</span><span class="sxs-lookup"><span data-stu-id="dff04-112">**Product B:** 1</span></span>
    - <span data-ttu-id="dff04-113">**Produkt C:** 2</span><span class="sxs-lookup"><span data-stu-id="dff04-113">**Product C:** 2</span></span>

- <span data-ttu-id="dff04-114">**Kostnadsberäkningsnivån** tilldelas följande strukturlistenivåer:</span><span class="sxs-lookup"><span data-stu-id="dff04-114">**Cost calculation level** assigns the following BOM levels:</span></span>

    - <span data-ttu-id="dff04-115">**Produkt A:** 0</span><span class="sxs-lookup"><span data-stu-id="dff04-115">**Product A:** 0</span></span>
    - <span data-ttu-id="dff04-116">**Produkt B:** 1</span><span class="sxs-lookup"><span data-stu-id="dff04-116">**Product B:** 1</span></span>
    - <span data-ttu-id="dff04-117">**Produkt C:** 2</span><span class="sxs-lookup"><span data-stu-id="dff04-117">**Product C:** 2</span></span>

<span data-ttu-id="dff04-118">En produktionsorder för produkt C skapas och produkt A läggs till i produktionsorderns strukturlista.</span><span class="sxs-lookup"><span data-stu-id="dff04-118">A production order for product C is then created, and product A is added to the production order BOM.</span></span> <span data-ttu-id="dff04-119">När ordern har uppskattats uppdateras strukturnivåerna på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="dff04-119">After the order is estimated, BOM levels are updated in the following way:</span></span>

- <span data-ttu-id="dff04-120">**Kostnadsnivån** tilldelas följande strukturlistenivåer:</span><span class="sxs-lookup"><span data-stu-id="dff04-120">**Costing level** assigns the following BOM levels:</span></span>

    - <span data-ttu-id="dff04-121">**Produkt B:** 1</span><span class="sxs-lookup"><span data-stu-id="dff04-121">**Product B:** 1</span></span>
    - <span data-ttu-id="dff04-122">**Produkt C:** 2</span><span class="sxs-lookup"><span data-stu-id="dff04-122">**Product C:** 2</span></span>
    - <span data-ttu-id="dff04-123">**Produkt A:** 3</span><span class="sxs-lookup"><span data-stu-id="dff04-123">**Product A:** 3</span></span>

- <span data-ttu-id="dff04-124">**Kostnadsberäkningsnivån** tilldelas följande strukturlistenivåer:</span><span class="sxs-lookup"><span data-stu-id="dff04-124">**Cost calculation level** assigns the following BOM levels:</span></span>

    - <span data-ttu-id="dff04-125">**Produkt A:** 0</span><span class="sxs-lookup"><span data-stu-id="dff04-125">**Product A:** 0</span></span>
    - <span data-ttu-id="dff04-126">**Produkt B:** 1</span><span class="sxs-lookup"><span data-stu-id="dff04-126">**Product B:** 1</span></span>
    - <span data-ttu-id="dff04-127">**Produkt C:** 2</span><span class="sxs-lookup"><span data-stu-id="dff04-127">**Product C:** 2</span></span>

<span data-ttu-id="dff04-128">Detta säkerställer att ändringar av strukturlistor för produktionsorder inte påverkar efterföljande kostnadsberäkningar.</span><span class="sxs-lookup"><span data-stu-id="dff04-128">This behavior ensures that changes to production order BOMs don't affect subsequent cost calculations.</span></span>
