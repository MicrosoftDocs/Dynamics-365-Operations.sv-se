---
title: Reservera samma batch för en försäljningsorder
description: Det här avsnittet innehåller en beskrivning av hur du ställer in en produkt om du vill tillåta lagerreservation mot en enda lagerbatch.
author: omulvad
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, EcoResStorageDimensionGroup, EcoResTrackingDimensionGroup, InventBatch, InventModelGroup, PdsAskSameLotForm, PdsCustSellableDays
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 28911
ms.assetid: 5823d75e-f839-46dd-beb3-e09b79fc8aa4
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: omulvad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2d6089d07b0f8bc1a36703b5b1c2f24af72770d5
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1568315"
---
# <a name="reserve-the-same-batch-for-a-sales-order"></a><span data-ttu-id="63af2-103">Reservera samma batch för en försäljningsorder</span><span class="sxs-lookup"><span data-stu-id="63af2-103">Reserve the same batch for a sales order</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="63af2-104">Det här avsnittet innehåller en beskrivning av hur du ställer in en produkt om du vill tillåta lagerreservation mot en enda lagerbatch.</span><span class="sxs-lookup"><span data-stu-id="63af2-104">This article explains how to set up a product to allow reservation of inventory against a single batch of inventory.</span></span>

<span data-ttu-id="63af2-105">Samma batchreservation gör att du kan du reservera lager för en försäljningsorderrad mot en enda lagerbatch.</span><span class="sxs-lookup"><span data-stu-id="63af2-105">Same batch reservation lets you reserve inventory for a sales order line against a single batch of inventory.</span></span> <span data-ttu-id="63af2-106">Till exempel kan en kund som beställer tapeter begära att hela ordern ska komma från samma parti för att undvika skillnader i trycket.</span><span class="sxs-lookup"><span data-stu-id="63af2-106">For example, a customer who orders wallpaper can request that the whole order be filled from the same batch or lot, to avoid inconsistencies among the rolls.</span></span> <span data-ttu-id="63af2-107">Om du vill ange att en produkt ska använda samma batchreservation, måste följande inställningar vara aktiva i artikelmodellgruppen, spårningsdimensionsgruppen och lagringsdimensionsgruppen som du tilldelar produkten:</span><span class="sxs-lookup"><span data-stu-id="63af2-107">To set up a product to use same batch reservation, the following settings must be active in the item model group, tracking dimension group, and storage dimension group that you assign to the product:</span></span>

-   <span data-ttu-id="63af2-108">**Artikelmodellgrupper** – Artikelmodellgruppen måste ha fälten **Urval från samma batch** och **Konsolidera behov** markerade i fältgruppen **Reservation** för lagerpolicyer.</span><span class="sxs-lookup"><span data-stu-id="63af2-108">**Item model groups** – The item model group must have the **Same batch selection** and **Consolidate requirement** fields selected in the **Reservation** field group for inventory policies.</span></span>
-   <span data-ttu-id="63af2-109">**Spårningsdimensionsgrupper** – Spårningsdimensionsgruppen måste ha fältet **Disponera per dimension** markerat för batchnumret.</span><span class="sxs-lookup"><span data-stu-id="63af2-109">**Tracking dimensions groups** – The tracking dimension group must have the **Coverage plan by dimension** field selected for the batch number.</span></span>
-   <span data-ttu-id="63af2-110">**Lagringsdimensionsgrupper** – Lagringsdimensionsgruppen måste ha fältet **Disponera per dimension** markerat för **Plats** och **Lagerställe**.</span><span class="sxs-lookup"><span data-stu-id="63af2-110">**Storage dimensions groups** – The storage dimension group must have the **Coverage plan by dimension** field selected for **Site** and **Warehouse**.</span></span>

<span data-ttu-id="63af2-111">När du reserverar lager för en produkt på en försäljningsorderrad som har ställts in för samma batchval försöker Microsoft Dynamics 365 for Finance and Operations att reservera den beställda kvantiteten från en enda lagerbatch.</span><span class="sxs-lookup"><span data-stu-id="63af2-111">When you reserve inventory for a product on a sales order line that is set up for same batch selection, Microsoft Dynamics 365 for Finance and Operations tries to reserve the ordered quantity from a single inventory batch.</span></span> <span data-ttu-id="63af2-112">Alla specifika batchattributkrav beaktas också.</span><span class="sxs-lookup"><span data-stu-id="63af2-112">Any specific batch attribute requirements are also considered.</span></span> <span data-ttu-id="63af2-113">Om kvantiteten inte kan fyllas från en enda batch visas sidan **Konflikt: samma batchreservation**.</span><span class="sxs-lookup"><span data-stu-id="63af2-113">If the quantity can't be filled from a single batch, the **Same batch reservation conflict** page appears.</span></span> <span data-ttu-id="63af2-114">På den här sidan beskrivs problemen och även de åtgärder du måste vidta om du vill fortsätta med reservationen.</span><span class="sxs-lookup"><span data-stu-id="63af2-114">This page describes the issues and also the actions that you can take to continue with the reservation.</span></span> <span data-ttu-id="63af2-115">Följande villkor kan hindra batchen från att reserveras:</span><span class="sxs-lookup"><span data-stu-id="63af2-115">The following conditions might prevent the batch from being reserved:</span></span>

-   <span data-ttu-id="63af2-116">Batchdispositionskoden har **Blockera reservation** för försäljningar som flaggas som **Spärrad**</span><span class="sxs-lookup"><span data-stu-id="63af2-116">The batch disposition code has **Block reservation** for sales flagged as **Blocked**.</span></span>
-   <span data-ttu-id="63af2-117">Batchen har förfallit, baserat på utgångsdatumet och eventuella gällande försäljningsdagar för kunden.</span><span class="sxs-lookup"><span data-stu-id="63af2-117">The batch has expired, based on the expiration date and any applicable customer sellable days.</span></span> <span data-ttu-id="63af2-118">Artikeln kan fortfarande användas för reservationer om artikelmodellgruppen för artikeln är FEFO – först utgått, först ut (First Expiry First Out) – och datumkontrollerat, och om bäst före-datumet har valts som plockvillkor.</span><span class="sxs-lookup"><span data-stu-id="63af2-118">The item can still be considered for reservation if the item model group for the item is First Expiry First Out (FEFO) date–controlled, and if the best-before date is selected as the pick criterion.</span></span>
-   <span data-ttu-id="63af2-119">Batchen inte har tillräcklig hållbarhetstid kvar, baserat på utgångsdatum och bäst före-datum, plus eventuella försäljningsdagar för kund.</span><span class="sxs-lookup"><span data-stu-id="63af2-119">The batch doesn't have enough shelf-life days remaining, based on the expiration date and best-before date, plus any customer sellable days.</span></span>




