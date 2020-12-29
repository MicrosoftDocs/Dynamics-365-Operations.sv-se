---
title: Bedömningsprofiler
description: I det här avsnittet beskrivs hur du ställer in data för bedömningsprofiler.
author: Henrikan
manager: ''
ms.date: 10/30/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSRatingProfile
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: henrikan
ms.search.validFrom: 2020-10-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3c54e7457813774027debd301d9a0bf8ce1b6d47
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/25/2020
ms.locfileid: "4646435"
---
# <a name="rating-profiles"></a><span data-ttu-id="684e5-103">Bedömningsprofiler</span><span class="sxs-lookup"><span data-stu-id="684e5-103">Rating profiles</span></span>

<span data-ttu-id="684e5-104">En bedömningsprofil påminner om ett logistik kontrakt (men inte ett juridiskt kontrakt).</span><span class="sxs-lookup"><span data-stu-id="684e5-104">A rating profile resembles a logistics contract (but not a legal contract).</span></span> <span data-ttu-id="684e5-105">Den används för att bestämma transporttaxor för laster.</span><span class="sxs-lookup"><span data-stu-id="684e5-105">It's used to determine transportation tariffs for loads.</span></span> 

<span data-ttu-id="684e5-106">Varje klassificeringsprofil är unik för ett transportföretag.</span><span class="sxs-lookup"><span data-stu-id="684e5-106">Each rating profile is unique to a shipping carrier.</span></span> <span data-ttu-id="684e5-107">I profilen kan du associera transportföretaget med ett tariffhuvud.</span><span class="sxs-lookup"><span data-stu-id="684e5-107">In the profile, you associate the shipping carrier with a rate master.</span></span> <span data-ttu-id="684e5-108">Tariffmallen definierar tariffbastilldelning och tariffbasen.</span><span class="sxs-lookup"><span data-stu-id="684e5-108">The rate master defines the rate base assignment and the rate base.</span></span> <span data-ttu-id="684e5-109">Tariffbasen bestämmer tariffen för transportföretaget.</span><span class="sxs-lookup"><span data-stu-id="684e5-109">The rate base determines the rate of the carrier.</span></span>

<span data-ttu-id="684e5-110">Du kan ställa in en klassificeringsprofil med hjälp av generisk sida som visar en översikt över alla befintliga.</span><span class="sxs-lookup"><span data-stu-id="684e5-110">You can set up a rating profile by using a generic page that shows an overview of all existing rating profiles.</span></span> <span data-ttu-id="684e5-111">Alternativt kan du ställa in klassificeringsprofilen direkt från transportföretaget.</span><span class="sxs-lookup"><span data-stu-id="684e5-111">Alternatively, you can set up a rating profile directly from the shipping carrier.</span></span> <span data-ttu-id="684e5-112">I båda fallen är informationen som du ställer in för värderingsprofilen densamma.</span><span class="sxs-lookup"><span data-stu-id="684e5-112">In both cases, the information that you set up for the rating profile is the same.</span></span>

## <a name="create-or-edit-a-rating-profile-on-the-rating-profiles-page"></a><span data-ttu-id="684e5-113">Skapa eller redigera en bedömningsprofil på sidan värderingsprofiler</span><span class="sxs-lookup"><span data-stu-id="684e5-113">Create or edit a rating profile on the Rating profiles page</span></span>

<span data-ttu-id="684e5-114">På sidan **bedömningsprofiler** kan du granska alla tillgängliga bedömningsprofiler.</span><span class="sxs-lookup"><span data-stu-id="684e5-114">On the **Rating profiles** page, you can review all available rating profiles.</span></span> <span data-ttu-id="684e5-115">Du kan också redigera befintliga profiler och skapa nya profiler.</span><span class="sxs-lookup"><span data-stu-id="684e5-115">You can also edit existing profiles and create new profiles.</span></span>

1. <span data-ttu-id="684e5-116">Gå till **Transporthantering \> Inställningar \> Bedömning \> Bedömningsprofil**.</span><span class="sxs-lookup"><span data-stu-id="684e5-116">Go to **Transportation management \> Setup \> Rating \> Rating profile**.</span></span>
1. <span data-ttu-id="684e5-117">I åtgärdsfönstret, välj **Ny** om du vill lägga till en ny bedömningsprofil i rutnätet eller välja **Redigera** för att redigera en befintlig profil.</span><span class="sxs-lookup"><span data-stu-id="684e5-117">On the Action Pane, select **New** to add a new rating profile to the grid, or select **Edit** to edit an existing profile.</span></span>
1. <span data-ttu-id="684e5-118">Ange följande fält i raden för den nya eller befintliga bedömningsprofil:</span><span class="sxs-lookup"><span data-stu-id="684e5-118">In the row for the new or existing rating profile, set the following fields:</span></span>

    - <span data-ttu-id="684e5-119">**Bedömningsprofil** – Ange en unik identifierare (ID) för betygsprofilen.</span><span class="sxs-lookup"><span data-stu-id="684e5-119">**Rating profile** – Enter a unique identifier (ID) for the rating profile.</span></span>
    - <span data-ttu-id="684e5-120">**Namn** – Ange ett beskrivande namn för bedömningsprofilen.</span><span class="sxs-lookup"><span data-stu-id="684e5-120">**Name** – Enter a descriptive name for the rating profile.</span></span>
    - <span data-ttu-id="684e5-121">**Transportföretag** – Välj ett transportföretag.</span><span class="sxs-lookup"><span data-stu-id="684e5-121">**Shipping carrier** – Select a shipping carrier.</span></span> <span data-ttu-id="684e5-122">Den bedömningsprofil som du ställer in visas också på sidan **Transportföretag** för det valda transportföretaget.</span><span class="sxs-lookup"><span data-stu-id="684e5-122">The rating profile that you're setting up will also be shown on the **Shipping carriers** page for the selected carrier.</span></span>
    - <span data-ttu-id="684e5-123">**Webbplats** och **Lagerställe** – Välj en webbplats och lagerställe.</span><span class="sxs-lookup"><span data-stu-id="684e5-123">**Site** and **Warehouse** – Select a site and warehouse.</span></span>
    - <span data-ttu-id="684e5-124">**Bedömningsmotor** – Välj bedömningsmotor för bedömningsprofilen.</span><span class="sxs-lookup"><span data-stu-id="684e5-124">**Rate engine** – Select the rate engine for the rating profile.</span></span>
    - <span data-ttu-id="684e5-125">**Bedömningsmall** – Välj bedömningsmall för bedömningsprofilen.</span><span class="sxs-lookup"><span data-stu-id="684e5-125">**Rate master** – Select the rate master for the rating profile.</span></span> <span data-ttu-id="684e5-126">Du kan använda tariffmallen för att definiera en tariffbastyp och en tariffbas.</span><span class="sxs-lookup"><span data-stu-id="684e5-126">You can use the rate master to define a rate base type and a rate base.</span></span> <span data-ttu-id="684e5-127">Mer information finns i [Ställ in tariffhuvuden](set-up-rate-masters.md).</span><span class="sxs-lookup"><span data-stu-id="684e5-127">For more information, see [Set up rate masters](set-up-rate-masters.md).</span></span>
    - <span data-ttu-id="684e5-128">**Transporttidsmotor** – Välj motorn för transporttid för värderingsprofilen.</span><span class="sxs-lookup"><span data-stu-id="684e5-128">**Transit time engine** – Select the transit time engine for the rating profile.</span></span>
    - <span data-ttu-id="684e5-129">**Bränsleindex för transportföretag** – Välj transporttidsmotor och transportföretagets bränsleindex för klassificeringsprofilen.</span><span class="sxs-lookup"><span data-stu-id="684e5-129">**Carrier fuel index** – Select the carrier fuel index for the rating profile.</span></span>
    - <span data-ttu-id="684e5-130">**Effektivt startdatum och tid** och **Effektivt slutdatum och tid** – Definiera den period då bedömningsprofilen ska vara aktiv.</span><span class="sxs-lookup"><span data-stu-id="684e5-130">**Effect start date and time** and **Effective end date and time** – Define the period when the rating profile should be active.</span></span>

1. <span data-ttu-id="684e5-131">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="684e5-131">On the Action Pane, select **Save**.</span></span>

## <a name="create-a-rating-profile-directly-on-the-shipping-carriers-page"></a><span data-ttu-id="684e5-132">Skapa en bedömningsprofil direkt på sidan transportföretag</span><span class="sxs-lookup"><span data-stu-id="684e5-132">Create a rating profile directly on the Shipping carriers page</span></span>

1. <span data-ttu-id="684e5-133">Gå till **Transporthantering \> Inställningar \> Transportföretag \> Transportföretag**.</span><span class="sxs-lookup"><span data-stu-id="684e5-133">Go to **Transportation management \> Setup \> Carriers \> Shipping carriers**.</span></span>
1. <span data-ttu-id="684e5-134">Välj ett transportföretag i listan.</span><span class="sxs-lookup"><span data-stu-id="684e5-134">Select a shipping carrier in the list.</span></span>
1. <span data-ttu-id="684e5-135">På snabbfliken **Bedömningsprofiler** välj **Ny** för att skapa en bedömningsprofil.</span><span class="sxs-lookup"><span data-stu-id="684e5-135">On the **Rating profiles** FastTab, select **New** to create a rating profile.</span></span>
1. <span data-ttu-id="684e5-136">Ange fälten för den nya bedömningsprofilen.</span><span class="sxs-lookup"><span data-stu-id="684e5-136">Set the fields for the new rating profile.</span></span> <span data-ttu-id="684e5-137">Fälten motsvarar fälten på sidan **bedömningsprofiler** enligt beskrivningen i föregående avsnitt i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="684e5-137">These fields correspond to the fields on the **Rating profiles** page, as described in previous section of this topic.</span></span>

> [!NOTE]
> <span data-ttu-id="684e5-138">Profiler som skapas på sidan **Transportföretag** visas också på sidan **Bedömningsprofiler**.</span><span class="sxs-lookup"><span data-stu-id="684e5-138">Profiles that are created on the **Shipping carriers** page are also shown on the **Rating profiles** page.</span></span>
