---
title: "Kringutrustning för kassa"
description: "Retail Modern point of sale (POS) och Cloud POS kan använda en mängd olika kassakringutrustning, med flera olika gränssnitt och tillämpningsalternativ för att uppfylla en återförsäljares olika verksamhetsscenarier."
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 215234
ms.assetid: 1893d4b3-e1b7-4b66-be58-0102addd5b36
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 4fbfb176f2504be8aaf67992d094da1daeefeb76
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="pos-hardware-peripherals"></a><span data-ttu-id="38fdc-103">Kringutrustning för kassa</span><span class="sxs-lookup"><span data-stu-id="38fdc-103">POS hardware peripherals</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="38fdc-104">Retail Modern point of sale (POS) och Cloud POS kan använda en mängd olika kassakringutrustning, med flera olika gränssnitt och tillämpningsalternativ för att uppfylla en återförsäljares olika verksamhetsscenarier.</span><span class="sxs-lookup"><span data-stu-id="38fdc-104">Retail Modern point of sale (POS) and Cloud POS can utilize a wide range of POS hardware peripherals, with multiple interfaces and deployment options to achieve a retailer’s various business scenarios.</span></span> 

<span data-ttu-id="38fdc-105">För att ge stöd för bredast möjliga enhetsurval oavsett tillverkare eller modell, använder kassan standardgränssnitt som exempelvis OLE for Retail POS (OPOS), enhetsdrivrutiner för Windows samt Windows point of service application program interfaces (API).</span><span class="sxs-lookup"><span data-stu-id="38fdc-105">To support the widest selection of devices across manufactures and models, POS utilizes standard interfaces such as OLE for Retail POS (OPOS), Windows device drivers, and Windows point of service application program interfaces (APIs).</span></span> <span data-ttu-id="38fdc-106">Generellt kommer kassan att fungera på dessa enheter förutsatt att rätt drivrutin finns tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="38fdc-106">Generally, POS will work on these devices provided that the appropriate driver is supplied.</span></span> <span data-ttu-id="38fdc-107">Eftersom varje tillverkares och programutvecklares implementering av dessa standardvärden emellertid kan variera, finns det ofta skillnader i vilka kvalifikationer eller beteenden som stöds.</span><span class="sxs-lookup"><span data-stu-id="38fdc-107">However, because each manufacturer and software developer’s implementation of these standards can vary, there are often differences in supported capabilities or behaviors.</span></span>

<span data-ttu-id="38fdc-108">Följande lista innehåller enhetsmodeller, i varje klass, som har testats internt av Microsoft.</span><span class="sxs-lookup"><span data-stu-id="38fdc-108">The following list includes device models, in each class, that have been tested internally by Microsoft.</span></span>

<span data-ttu-id="38fdc-109">**OPOS-enheter**</span><span class="sxs-lookup"><span data-stu-id="38fdc-109">**OPOS devices**</span></span>

-   <span data-ttu-id="38fdc-110">Streckkod – Motorola DS9208</span><span class="sxs-lookup"><span data-stu-id="38fdc-110">Barcode – Motorola DS9208</span></span>
-   <span data-ttu-id="38fdc-111">MSR – HP IDRA-334133, Magtek PN - 21073062</span><span class="sxs-lookup"><span data-stu-id="38fdc-111">MSR – HP IDRA-334133, Magtek PN - 21073062</span></span>
-   <span data-ttu-id="38fdc-112">LineDisplay – Epson M58DC</span><span class="sxs-lookup"><span data-stu-id="38fdc-112">LineDisplay – Epson M58DC</span></span>
-   <span data-ttu-id="38fdc-113">Pinpad – Verifone 1000SE</span><span class="sxs-lookup"><span data-stu-id="38fdc-113">Pinpad – Verifone 1000SE</span></span>
-   <span data-ttu-id="38fdc-114">Signaturblock – Scriptel ST1550</span><span class="sxs-lookup"><span data-stu-id="38fdc-114">Signature pad – Scriptel ST1550</span></span>
-   <span data-ttu-id="38fdc-115">Skrivare – EPSON TM-T88IV, TMT88V</span><span class="sxs-lookup"><span data-stu-id="38fdc-115">Printer – EPSON TM-T88IV, TMT88V</span></span>
-   <span data-ttu-id="38fdc-116">Kassa – Star SMD2-1317BK44</span><span class="sxs-lookup"><span data-stu-id="38fdc-116">Cash drawer – Star SMD2-1317BK44</span></span>
-   <span data-ttu-id="38fdc-117">Skala – Datalogic Magellan 8400</span><span class="sxs-lookup"><span data-stu-id="38fdc-117">Scale – Datalogic Magellan 8400</span></span>

<span data-ttu-id="38fdc-118">**Tangentbords-wedge MSR**</span><span class="sxs-lookup"><span data-stu-id="38fdc-118">**Keyboard wedge MSR**</span></span>

-   <span data-ttu-id="38fdc-119">Magtek USB</span><span class="sxs-lookup"><span data-stu-id="38fdc-119">Magtek USB</span></span>

<span data-ttu-id="38fdc-120">**Betalterminal**</span><span class="sxs-lookup"><span data-stu-id="38fdc-120">**Payment terminal**</span></span>

-   <span data-ttu-id="38fdc-121">Equinox L3500</span><span class="sxs-lookup"><span data-stu-id="38fdc-121">Equinox L3500</span></span>
-   <span data-ttu-id="38fdc-122">Verifone MX925</span><span class="sxs-lookup"><span data-stu-id="38fdc-122">Verifone MX925</span></span>

<span data-ttu-id="38fdc-123">**Nätverksenheter**</span><span class="sxs-lookup"><span data-stu-id="38fdc-123">**Network devices**</span></span>

-   <span data-ttu-id="38fdc-124">Skrivare – Star TSP650II</span><span class="sxs-lookup"><span data-stu-id="38fdc-124">Printer – Star TSP650II</span></span>
-   <span data-ttu-id="38fdc-125">Kassa – APG Atwood</span><span class="sxs-lookup"><span data-stu-id="38fdc-125">Cash drawer – APG Atwood</span></span>
-   <span data-ttu-id="38fdc-126">Betalterminal – MX915, MX925</span><span class="sxs-lookup"><span data-stu-id="38fdc-126">Payment terminal – MX915, MX925</span></span>

<span data-ttu-id="38fdc-127">**MPOS styr endast IPC**</span><span class="sxs-lookup"><span data-stu-id="38fdc-127">**MPOS direct IPC only**</span></span>

-   <span data-ttu-id="38fdc-128">Streckkod – Honeywell 1900, HP LS2208</span><span class="sxs-lookup"><span data-stu-id="38fdc-128">Barcode – Honeywell 1900, HP LS2208</span></span>
-   <span data-ttu-id="38fdc-129">MSR – Magtek PN - 21073075</span><span class="sxs-lookup"><span data-stu-id="38fdc-129">MSR – Magtek PN - 21073075</span></span>





