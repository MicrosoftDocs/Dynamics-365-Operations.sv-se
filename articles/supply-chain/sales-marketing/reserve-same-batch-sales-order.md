---
title: Reservera samma batch för en försäljningsorder
description: Det här avsnittet innehåller en beskrivning av hur du ställer in en produkt om du vill tillåta lagerreservation mot en enda lagerbatch.
author: omulvad
manager: tfehr
ms.date: 03/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, EcoResStorageDimensionGroup, EcoResTrackingDimensionGroup, InventBatch, InventModelGroup, PdsAskSameLotForm, PdsCustSellableDays
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 28911
ms.assetid: 5823d75e-f839-46dd-beb3-e09b79fc8aa4
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 29fd7afdd032e5d3afbe90a1883783b0f2dd83e2
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/10/2020
ms.locfileid: "3982171"
---
# <a name="reserve-the-same-batch-for-a-sales-order"></a><span data-ttu-id="f502e-103">Reservera samma batch för en försäljningsorder</span><span class="sxs-lookup"><span data-stu-id="f502e-103">Reserve the same batch for a sales order</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f502e-104">Det här avsnittet innehåller en beskrivning av hur du ställer in en produkt om du vill tillåta lagerreservation mot en enda lagerbatch.</span><span class="sxs-lookup"><span data-stu-id="f502e-104">This article explains how to set up a product to allow reservation of inventory against a single batch of inventory.</span></span>

<span data-ttu-id="f502e-105">Samma batchreservation gör att du kan du reservera lager för en försäljningsorderrad mot en enda lagerbatch.</span><span class="sxs-lookup"><span data-stu-id="f502e-105">Same batch reservation lets you reserve inventory for a sales order line against a single batch of inventory.</span></span> <span data-ttu-id="f502e-106">Till exempel kan en kund som beställer tapeter begära att hela ordern ska komma från samma parti för att undvika skillnader i trycket.</span><span class="sxs-lookup"><span data-stu-id="f502e-106">For example, a customer who orders wallpaper can request that the whole order be filled from the same batch or lot, to avoid inconsistencies among the rolls.</span></span> <span data-ttu-id="f502e-107">Om du vill ange att en produkt ska använda samma batchreservation, måste följande inställningar vara aktiva i artikelmodellgruppen, spårningsdimensionsgruppen och lagringsdimensionsgruppen som du tilldelar produkten:</span><span class="sxs-lookup"><span data-stu-id="f502e-107">To set up a product to use same batch reservation, the following settings must be active in the item model group, tracking dimension group, and storage dimension group that you assign to the product:</span></span>

- <span data-ttu-id="f502e-108">**Artikelmodellgrupper** – Artikelmodellgruppen måste ha fälten **Urval från samma batch** och **Konsolidera behov** markerade i fältgruppen **Reservation** för lagerpolicyer.</span><span class="sxs-lookup"><span data-stu-id="f502e-108">**Item model groups** – The item model group must have the **Same batch selection** and **Consolidate requirement** fields selected in the **Reservation** field group for inventory policies.</span></span>
- <span data-ttu-id="f502e-109">**Spårningsdimensionsgrupper** – Spårningsdimensionsgruppen måste ha fältet **Disponera per dimension** markerat för batchnumret.</span><span class="sxs-lookup"><span data-stu-id="f502e-109">**Tracking dimensions groups** – The tracking dimension group must have the **Coverage plan by dimension** field selected for the batch number.</span></span>
- <span data-ttu-id="f502e-110">**Lagringsdimensionsgrupper** – Lagringsdimensionsgruppen måste ha fältet **Disponera per dimension** markerat för **Plats** och **Lagerställe**.</span><span class="sxs-lookup"><span data-stu-id="f502e-110">**Storage dimensions groups** – The storage dimension group must have the **Coverage plan by dimension** field selected for **Site** and **Warehouse**.</span></span>

<span data-ttu-id="f502e-111">När du reserverar lager för en produkt på en försäljningsorderrad som har ställts in för samma batchval försöker systemet att reservera den beställda kvantiteten från en enda lagerbatch.</span><span class="sxs-lookup"><span data-stu-id="f502e-111">When you reserve inventory for a product on a sales order line that is set up for same batch selection, the system tries to reserve the ordered quantity from a single inventory batch.</span></span> <span data-ttu-id="f502e-112">Alla specifika batchattributkrav beaktas också.</span><span class="sxs-lookup"><span data-stu-id="f502e-112">Any specific batch attribute requirements are also considered.</span></span> <span data-ttu-id="f502e-113">Om kvantiteten inte kan fyllas från en enda batch visas sidan **Konflikt: samma batchreservation**.</span><span class="sxs-lookup"><span data-stu-id="f502e-113">If the quantity can't be filled from a single batch, the **Same batch reservation conflict** page appears.</span></span> <span data-ttu-id="f502e-114">På den här sidan beskrivs problemen och även de åtgärder du måste vidta om du vill fortsätta med reservationen.</span><span class="sxs-lookup"><span data-stu-id="f502e-114">This page describes the issues and also the actions that you can take to continue with the reservation.</span></span> <span data-ttu-id="f502e-115">Följande villkor kan hindra batchen från att reserveras:</span><span class="sxs-lookup"><span data-stu-id="f502e-115">The following conditions might prevent the batch from being reserved:</span></span>

- <span data-ttu-id="f502e-116">Batchdispositionskoden har **Blockera reservation** för försäljningar som flaggas som **Spärrad**</span><span class="sxs-lookup"><span data-stu-id="f502e-116">The batch disposition code has **Block reservation** for sales flagged as **Blocked**.</span></span>
- <span data-ttu-id="f502e-117">Batchen har förfallit, baserat på utgångsdatumet och eventuella gällande försäljningsdagar för kunden.</span><span class="sxs-lookup"><span data-stu-id="f502e-117">The batch has expired, based on the expiration date and any applicable customer sellable days.</span></span> <span data-ttu-id="f502e-118">Artikeln kan fortfarande användas för reservationer om artikelmodellgruppen för artikeln är FEFO – först utgått, först ut (First Expiry First Out) – och datumkontrollerat, och om bäst före-datumet har valts som plockvillkor.</span><span class="sxs-lookup"><span data-stu-id="f502e-118">The item can still be considered for reservation if the item model group for the item is First Expiry First Out (FEFO) date–controlled, and if the best-before date is selected as the pick criterion.</span></span>
- <span data-ttu-id="f502e-119">Batchen inte har tillräcklig hållbarhetstid kvar, baserat på utgångsdatum och bäst före-datum, plus eventuella försäljningsdagar för kund.</span><span class="sxs-lookup"><span data-stu-id="f502e-119">The batch doesn't have enough shelf-life days remaining, based on the expiration date and best-before date, plus any customer sellable days.</span></span>

<span data-ttu-id="f502e-120">För artiklar som är kopplade till en lagringsdimensionsgrupp som har **Använd lagerstyrningsprocesser** aktiverat kan du reservera specifika batchnummer genom att använda en reservationssekvens med den lagerdimension som definierats ovanför platsdimensionen.</span><span class="sxs-lookup"><span data-stu-id="f502e-120">For items associated with a storage dimension group that has **Use warehouse management processes** enabled, you can reserve specific batch numbers by using a reservation hierarchy with the batch number inventory dimension defined above the location dimension.</span></span> <span data-ttu-id="f502e-121">Sidan **Batch-reservation** för försäljnings- och överföringsorderrader låter dig också välja och reservera flera rader baserat på tillgängliga batchnummer.</span><span class="sxs-lookup"><span data-stu-id="f502e-121">The **Batch reservation** page for sales and transfer order lines also lets you select and reserve multiple lines based on the available batch numbers.</span></span> <span data-ttu-id="f502e-122">Mer information om vad du ska göra om du använder en reservationssekvens med dimensionen för batchnumret under platsen finns i [Flexibel reservationspolicy för dimension på lagernivå](../warehousing/flexible-warehouse-level-dimension-reservation.md).</span><span class="sxs-lookup"><span data-stu-id="f502e-122">For more information about what to do if you are using a reservation hierarchy that has the batch number dimension below the location, see [Flexible warehouse-level dimension reservation policy](../warehousing/flexible-warehouse-level-dimension-reservation.md).</span></span>
