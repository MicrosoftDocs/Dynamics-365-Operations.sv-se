---
title: "Systemgruppering i en öppen arbetslista"
description: "Det här avsnittet beskriver hur du filtrerar den öppna arbetslistan på en mobil enhet."
author: Mirzaab
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSRFMenuItem
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 029511634e56aec7fdd91bad9441cd12951fbd8d
ms.openlocfilehash: 3592094d09a8596f88c44d869b22035a126fab69
ms.contentlocale: sv-se
ms.lasthandoff: 01/17/2018

---

# <a name="system-grouping-on-an-open-work-list"></a><span data-ttu-id="c3418-103">Systemgruppering i en öppen arbetslista</span><span class="sxs-lookup"><span data-stu-id="c3418-103">System grouping on an open work list</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="c3418-104">Genom att använda ett systemgrupperingsfält kan de filtrera en öppen arbetslista utan att behöva redigera menyalternativet mobil enhet.</span><span class="sxs-lookup"><span data-stu-id="c3418-104">By using a system grouping field, you can filter an open work list without having to edit the mobile device menu item.</span></span>
<span data-ttu-id="c3418-105">Där det går att tillämpa fungerar systemgrupperingen för att filtrera en arbetslista i ett fält för en enskild arbetsrubrik.</span><span class="sxs-lookup"><span data-stu-id="c3418-105">Where it applies, system grouping works for filtering a work list on a single work header field.</span></span> <span data-ttu-id="c3418-106">Du kan inte använda systemgruppering för att filtrera på radnivåfält.</span><span class="sxs-lookup"><span data-stu-id="c3418-106">You cannot use system grouping to filter on line level fields.</span></span>

## <a name="set-up-system-grouping-on-an-open-work-list"></a><span data-ttu-id="c3418-107">Ställa in systemgruppering i en öppen arbetslista</span><span class="sxs-lookup"><span data-stu-id="c3418-107">Set up system grouping on an open work list</span></span>
<span data-ttu-id="c3418-108">Använd dessa steg för att ställa in systemgruppering i en öppen arbetslista.</span><span class="sxs-lookup"><span data-stu-id="c3418-108">Use these steps to set up system grouping on an open work list.</span></span>

-   <span data-ttu-id="c3418-109">Från ett menyalternativ för en mobil enhet, välj **Läge: indirekt** och **Aktivitetskod: Visa öppna arbetslista**.</span><span class="sxs-lookup"><span data-stu-id="c3418-109">From a mobile device menu item, select **Mode: Indirect** and **Activity Code: Display open work list**.</span></span> <span data-ttu-id="c3418-110">Följande alternativ blir tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="c3418-110">The following options become available.</span></span> <span data-ttu-id="c3418-111">Dessa alternativ krävs för systemgruppering av en öppen arbetslista.</span><span class="sxs-lookup"><span data-stu-id="c3418-111">These options are required for system grouping on an open work list.</span></span> 

| <span data-ttu-id="c3418-112">Alternativ</span><span class="sxs-lookup"><span data-stu-id="c3418-112">Option</span></span>        | <span data-ttu-id="c3418-113">beskrivning</span><span class="sxs-lookup"><span data-stu-id="c3418-113">Description</span></span>   | 
| ------------- | ------------- |
| <span data-ttu-id="c3418-114">Tillåta systemgruppering</span><span class="sxs-lookup"><span data-stu-id="c3418-114">Allow system grouping</span></span>   | <span data-ttu-id="c3418-115">Möjliggör systemgruppering för ett menyalternativ i en vald arbetslista.</span><span class="sxs-lookup"><span data-stu-id="c3418-115">Enables system groping for a selected work list menu item.</span></span>| 
| <span data-ttu-id="c3418-116">Fält för systemgruppering</span><span class="sxs-lookup"><span data-stu-id="c3418-116">System grouping field</span></span>   | <span data-ttu-id="c3418-117">Endast tillgängligt om **Tillåt systemarbete** anges till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="c3418-117">Available only if **Allow system work** is set to **Yes**.</span></span> <span data-ttu-id="c3418-118">Välj det fält som bestämmer hur plockningsarbete för arbetare ska grupperas.</span><span class="sxs-lookup"><span data-stu-id="c3418-118">Select the field that determines how picking work will be grouped for workers.</span></span> <span data-ttu-id="c3418-119">Om du till exempel väljer fältet **ShipmentId** kommer arbetstagare att skanna leverans-ID:t för att gruppera plockningsarbetet.</span><span class="sxs-lookup"><span data-stu-id="c3418-119">For example, if you select the **ShipmentId** field, the worker will scan the shipment ID to group the picking work.</span></span> <span data-ttu-id="c3418-120">Allt arbete för leveransen tilldelas sedan till arbetaren.</span><span class="sxs-lookup"><span data-stu-id="c3418-120">All work for the shipment is then assigned to the worker.</span></span> <span data-ttu-id="c3418-121">Detta fält kräver att du skapar ett menyalternativ som ska använda befintligt arbete som grupperas av systemet.</span><span class="sxs-lookup"><span data-stu-id="c3418-121">This field requires that you create a menu item to use existing work that is grouped by the system.</span></span> <span data-ttu-id="c3418-122">Använd fältet **Etikett för systemgruppering** för att informera arbetaren om vad denne ska skanna.</span><span class="sxs-lookup"><span data-stu-id="c3418-122">Use the **System grouping label** field to inform the worker what to scan.</span></span> |
| <span data-ttu-id="c3418-123">Etikett för systemgruppering</span><span class="sxs-lookup"><span data-stu-id="c3418-123">System grouping label</span></span>   | <span data-ttu-id="c3418-124">Endast tillgängligt om **Tillåt systemarbete** anges till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="c3418-124">Available only if **Allow system work** is set to **Yes**.</span></span> <span data-ttu-id="c3418-125">Ange text för att informera arbetstagaren om vad som ska skannas när plockningsarbetet grupperas .</span><span class="sxs-lookup"><span data-stu-id="c3418-125">Enter information for the worker about what to scan when picking work is grouped.</span></span> <span data-ttu-id="c3418-126">Om du till exempel använder fältet **ShipmentId** för att gruppera plockningarbete efter leverans kan du ange Leverans-ID i fältet.</span><span class="sxs-lookup"><span data-stu-id="c3418-126">For example, if you use the **ShipmentId** field to group picking work by shipment, you might enter Shipment ID in the field.</span></span> <span data-ttu-id="c3418-127">Detta fält kräver att du skapar ett menyalternativ som ska använda befintligt arbete som grupperas av systemet.</span><span class="sxs-lookup"><span data-stu-id="c3418-127">This field requires that you create a menu item to use existing work that is grouped by the system.</span></span> <span data-ttu-id="c3418-128">Du måste också välja fältet som du vill gruppera efter i fältet **Systemgruppering**.</span><span class="sxs-lookup"><span data-stu-id="c3418-128">You must also select the field to group by in the **System grouping** field.</span></span>|

