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
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2020-04-23
ms.dyn365.ops.version: Release 10.0.12
ms.openlocfilehash: 1cfbbb6aadbd24a0352776285f6c60ff10f59549
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5251036"
---
# <a name="cost-calculation-level"></a><span data-ttu-id="79c94-104">Kostnadsberäkningsnivå</span><span class="sxs-lookup"><span data-stu-id="79c94-104">Cost calculation level</span></span>

<span data-ttu-id="79c94-105">Den strukturlistenivå som har den namngivna **kostnadsberäknings nivån** utesluter produktionsorder och batchorder från sina beräkningar.</span><span class="sxs-lookup"><span data-stu-id="79c94-105">The bill of materials (BOM) level that is named **Cost calculation level** excludes production orders and batch orders from its calculations.</span></span> <span data-ttu-id="79c94-106">Systemet använder den här nivån när kostnadsberäkningar i kostnadsversioner körs.</span><span class="sxs-lookup"><span data-stu-id="79c94-106">The system uses this level when it runs cost calculations in costing versions.</span></span> <span data-ttu-id="79c94-107">I processer som omberäkningar och lagerstängningar använder systemet strukturlistenivån **Kostnadsnivå** i stället.</span><span class="sxs-lookup"><span data-stu-id="79c94-107">In processes such as recalculation and inventory close, the system uses the **Costing level** BOM level instead.</span></span>

<span data-ttu-id="79c94-108">Följande enkla scenario visar skillnaderna mellan **kostnadsberäkningsnivån** och strukturnivån på **kostnadsnivån**.</span><span class="sxs-lookup"><span data-stu-id="79c94-108">The following simple scenario shows the differences between the **Cost calculation level** BOM level and the **Costing level** BOM level.</span></span>

<span data-ttu-id="79c94-109">Du har tre produkter: A, B och C. Produkt C är komponenten av produkt B och produkt B är komponenten av produkt A.</span><span class="sxs-lookup"><span data-stu-id="79c94-109">You have three products: A, B, and C. Product C is the component of product B, and product B is the component of product A.</span></span>

- <span data-ttu-id="79c94-110">**Kostnadsnivån** tilldelas följande strukturlistenivåer:</span><span class="sxs-lookup"><span data-stu-id="79c94-110">**Costing level** assigns the following BOM levels:</span></span>

    - <span data-ttu-id="79c94-111">**Produkt A:** 0</span><span class="sxs-lookup"><span data-stu-id="79c94-111">**Product A:** 0</span></span>
    - <span data-ttu-id="79c94-112">**Produkt B:** 1</span><span class="sxs-lookup"><span data-stu-id="79c94-112">**Product B:** 1</span></span>
    - <span data-ttu-id="79c94-113">**Produkt C:** 2</span><span class="sxs-lookup"><span data-stu-id="79c94-113">**Product C:** 2</span></span>

- <span data-ttu-id="79c94-114">**Kostnadsberäkningsnivån** tilldelas följande strukturlistenivåer:</span><span class="sxs-lookup"><span data-stu-id="79c94-114">**Cost calculation level** assigns the following BOM levels:</span></span>

    - <span data-ttu-id="79c94-115">**Produkt A:** 0</span><span class="sxs-lookup"><span data-stu-id="79c94-115">**Product A:** 0</span></span>
    - <span data-ttu-id="79c94-116">**Produkt B:** 1</span><span class="sxs-lookup"><span data-stu-id="79c94-116">**Product B:** 1</span></span>
    - <span data-ttu-id="79c94-117">**Produkt C:** 2</span><span class="sxs-lookup"><span data-stu-id="79c94-117">**Product C:** 2</span></span>

<span data-ttu-id="79c94-118">En produktionsorder för produkt C skapas och produkt A läggs till i produktionsorderns strukturlista.</span><span class="sxs-lookup"><span data-stu-id="79c94-118">A production order for product C is then created, and product A is added to the production order BOM.</span></span> <span data-ttu-id="79c94-119">När ordern har uppskattats uppdateras strukturnivåerna på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="79c94-119">After the order is estimated, BOM levels are updated in the following way:</span></span>

- <span data-ttu-id="79c94-120">**Kostnadsnivån** tilldelas följande strukturlistenivåer:</span><span class="sxs-lookup"><span data-stu-id="79c94-120">**Costing level** assigns the following BOM levels:</span></span>

    - <span data-ttu-id="79c94-121">**Produkt B:** 1</span><span class="sxs-lookup"><span data-stu-id="79c94-121">**Product B:** 1</span></span>
    - <span data-ttu-id="79c94-122">**Produkt C:** 2</span><span class="sxs-lookup"><span data-stu-id="79c94-122">**Product C:** 2</span></span>
    - <span data-ttu-id="79c94-123">**Produkt A:** 3</span><span class="sxs-lookup"><span data-stu-id="79c94-123">**Product A:** 3</span></span>

- <span data-ttu-id="79c94-124">**Kostnadsberäkningsnivån** tilldelas följande strukturlistenivåer:</span><span class="sxs-lookup"><span data-stu-id="79c94-124">**Cost calculation level** assigns the following BOM levels:</span></span>

    - <span data-ttu-id="79c94-125">**Produkt A:** 0</span><span class="sxs-lookup"><span data-stu-id="79c94-125">**Product A:** 0</span></span>
    - <span data-ttu-id="79c94-126">**Produkt B:** 1</span><span class="sxs-lookup"><span data-stu-id="79c94-126">**Product B:** 1</span></span>
    - <span data-ttu-id="79c94-127">**Produkt C:** 2</span><span class="sxs-lookup"><span data-stu-id="79c94-127">**Product C:** 2</span></span>

<span data-ttu-id="79c94-128">Detta säkerställer att ändringar av strukturlistor för produktionsorder inte påverkar efterföljande kostnadsberäkningar.</span><span class="sxs-lookup"><span data-stu-id="79c94-128">This behavior ensures that changes to production order BOMs don't affect subsequent cost calculations.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]