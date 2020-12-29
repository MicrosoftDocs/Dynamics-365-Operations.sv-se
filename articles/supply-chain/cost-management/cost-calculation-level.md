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
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437579"
---
# <a name="cost-calculation-level"></a><span data-ttu-id="caeb1-104">Kostnadsberäkningsnivå</span><span class="sxs-lookup"><span data-stu-id="caeb1-104">Cost calculation level</span></span>

<span data-ttu-id="caeb1-105">Den strukturlistenivå som har den namngivna **kostnadsberäknings nivån** utesluter produktionsorder och batchorder från sina beräkningar.</span><span class="sxs-lookup"><span data-stu-id="caeb1-105">The bill of materials (BOM) level that is named **Cost calculation level** excludes production orders and batch orders from its calculations.</span></span> <span data-ttu-id="caeb1-106">Systemet använder den här nivån när kostnadsberäkningar i kostnadsversioner körs.</span><span class="sxs-lookup"><span data-stu-id="caeb1-106">The system uses this level when it runs cost calculations in costing versions.</span></span> <span data-ttu-id="caeb1-107">I processer som omberäkningar och lagerstängningar använder systemet strukturlistenivån **Kostnadsnivå** i stället.</span><span class="sxs-lookup"><span data-stu-id="caeb1-107">In processes such as recalculation and inventory close, the system uses the **Costing level** BOM level instead.</span></span>

<span data-ttu-id="caeb1-108">Följande enkla scenario visar skillnaderna mellan **kostnadsberäkningsnivån** och strukturnivån på **kostnadsnivån**.</span><span class="sxs-lookup"><span data-stu-id="caeb1-108">The following simple scenario shows the differences between the **Cost calculation level** BOM level and the **Costing level** BOM level.</span></span>

<span data-ttu-id="caeb1-109">Du har tre produkter: A, B och C. Produkt C är komponenten av produkt B och produkt B är komponenten av produkt A.</span><span class="sxs-lookup"><span data-stu-id="caeb1-109">You have three products: A, B, and C. Product C is the component of product B, and product B is the component of product A.</span></span>

- <span data-ttu-id="caeb1-110">**Kostnadsnivån** tilldelas följande strukturlistenivåer:</span><span class="sxs-lookup"><span data-stu-id="caeb1-110">**Costing level** assigns the following BOM levels:</span></span>

    - <span data-ttu-id="caeb1-111">**Produkt A:** 0</span><span class="sxs-lookup"><span data-stu-id="caeb1-111">**Product A:** 0</span></span>
    - <span data-ttu-id="caeb1-112">**Produkt B:** 1</span><span class="sxs-lookup"><span data-stu-id="caeb1-112">**Product B:** 1</span></span>
    - <span data-ttu-id="caeb1-113">**Produkt C:** 2</span><span class="sxs-lookup"><span data-stu-id="caeb1-113">**Product C:** 2</span></span>

- <span data-ttu-id="caeb1-114">**Kostnadsberäkningsnivån** tilldelas följande strukturlistenivåer:</span><span class="sxs-lookup"><span data-stu-id="caeb1-114">**Cost calculation level** assigns the following BOM levels:</span></span>

    - <span data-ttu-id="caeb1-115">**Produkt A:** 0</span><span class="sxs-lookup"><span data-stu-id="caeb1-115">**Product A:** 0</span></span>
    - <span data-ttu-id="caeb1-116">**Produkt B:** 1</span><span class="sxs-lookup"><span data-stu-id="caeb1-116">**Product B:** 1</span></span>
    - <span data-ttu-id="caeb1-117">**Produkt C:** 2</span><span class="sxs-lookup"><span data-stu-id="caeb1-117">**Product C:** 2</span></span>

<span data-ttu-id="caeb1-118">En produktionsorder för produkt C skapas och produkt A läggs till i produktionsorderns strukturlista.</span><span class="sxs-lookup"><span data-stu-id="caeb1-118">A production order for product C is then created, and product A is added to the production order BOM.</span></span> <span data-ttu-id="caeb1-119">När ordern har uppskattats uppdateras strukturnivåerna på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="caeb1-119">After the order is estimated, BOM levels are updated in the following way:</span></span>

- <span data-ttu-id="caeb1-120">**Kostnadsnivån** tilldelas följande strukturlistenivåer:</span><span class="sxs-lookup"><span data-stu-id="caeb1-120">**Costing level** assigns the following BOM levels:</span></span>

    - <span data-ttu-id="caeb1-121">**Produkt B:** 1</span><span class="sxs-lookup"><span data-stu-id="caeb1-121">**Product B:** 1</span></span>
    - <span data-ttu-id="caeb1-122">**Produkt C:** 2</span><span class="sxs-lookup"><span data-stu-id="caeb1-122">**Product C:** 2</span></span>
    - <span data-ttu-id="caeb1-123">**Produkt A:** 3</span><span class="sxs-lookup"><span data-stu-id="caeb1-123">**Product A:** 3</span></span>

- <span data-ttu-id="caeb1-124">**Kostnadsberäkningsnivån** tilldelas följande strukturlistenivåer:</span><span class="sxs-lookup"><span data-stu-id="caeb1-124">**Cost calculation level** assigns the following BOM levels:</span></span>

    - <span data-ttu-id="caeb1-125">**Produkt A:** 0</span><span class="sxs-lookup"><span data-stu-id="caeb1-125">**Product A:** 0</span></span>
    - <span data-ttu-id="caeb1-126">**Produkt B:** 1</span><span class="sxs-lookup"><span data-stu-id="caeb1-126">**Product B:** 1</span></span>
    - <span data-ttu-id="caeb1-127">**Produkt C:** 2</span><span class="sxs-lookup"><span data-stu-id="caeb1-127">**Product C:** 2</span></span>

<span data-ttu-id="caeb1-128">Detta säkerställer att ändringar av strukturlistor för produktionsorder inte påverkar efterföljande kostnadsberäkningar.</span><span class="sxs-lookup"><span data-stu-id="caeb1-128">This behavior ensures that changes to production order BOMs don't affect subsequent cost calculations.</span></span>
