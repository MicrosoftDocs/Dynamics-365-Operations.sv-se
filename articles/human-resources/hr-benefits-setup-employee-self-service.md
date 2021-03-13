---
title: Konfigurera självbetjäning för medarbetare
description: I Microsoft Dynamics 365 Human Resources kan du konfigurera paneler för navigering på högsta nivå i Självbetjäning för medarbetare.
author: andreabichsel
manager: tfehr
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 32981812eac3c08e1409fe5470b550e421f5d6c9
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/03/2021
ms.locfileid: "5114294"
---
# <a name="configure-employee-self-service"></a><span data-ttu-id="e8baa-103">Konfigurera självbetjäning för medarbetare</span><span class="sxs-lookup"><span data-stu-id="e8baa-103">Configure employee self service</span></span>

<span data-ttu-id="e8baa-104">I Microsoft Dynamics 365 Human Resources kan du konfigurera paneler för navigering på högsta nivå i Självbetjäning för medarbetare.</span><span class="sxs-lookup"><span data-stu-id="e8baa-104">In Microsoft Dynamics 365 Human Resources, you can configure tiles for top-level navigation in Employee self service.</span></span> <span data-ttu-id="e8baa-105">Paneler för förmånsplaner dirigerar användare till förmånsplaner som de berättigar till.</span><span class="sxs-lookup"><span data-stu-id="e8baa-105">Benefit plan tiles direct users to benefit plans that they're eligible for.</span></span>

## <a name="set-up-a-benefit-plans-tile"></a><span data-ttu-id="e8baa-106">Ställa in panel för förmånsplan</span><span class="sxs-lookup"><span data-stu-id="e8baa-106">Set up a benefit plans tile</span></span>

1. <span data-ttu-id="e8baa-107">I arbetsytan **Förmånshantering** under **inställningar**, välj **Medarbetarens självbetjäningsparametrar**.</span><span class="sxs-lookup"><span data-stu-id="e8baa-107">In the **Benefits management** workspace, under **Setup**, select **Employee self service parameters**.</span></span>

2. <span data-ttu-id="e8baa-108">Välj fliken **Inställning av paneler för förmånsplaner** och välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="e8baa-108">Select the **Benefit plans tile setup** tab, and then select **New**.</span></span>

3. <span data-ttu-id="e8baa-109">Ange värden för de följande fälten:</span><span class="sxs-lookup"><span data-stu-id="e8baa-109">Specify values for the following fields:</span></span>

   | <span data-ttu-id="e8baa-110">Fält</span><span class="sxs-lookup"><span data-stu-id="e8baa-110">Field</span></span> | <span data-ttu-id="e8baa-111">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="e8baa-111">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="e8baa-112">**Panel-ID**</span><span class="sxs-lookup"><span data-stu-id="e8baa-112">**Tile ID**</span></span> | <span data-ttu-id="e8baa-113">Unik identifierare för panelen.</span><span class="sxs-lookup"><span data-stu-id="e8baa-113">The unique identifier for the tile.</span></span> |
   | <span data-ttu-id="e8baa-114">**Etikettext för panel**</span><span class="sxs-lookup"><span data-stu-id="e8baa-114">**Tile label text**</span></span> | <span data-ttu-id="e8baa-115">Texten som visas för panelen på självbetjäning.</span><span class="sxs-lookup"><span data-stu-id="e8baa-115">The text that will appear for the tile on Self-service.</span></span> |
   | <span data-ttu-id="e8baa-116">**Beskrivning**</span><span class="sxs-lookup"><span data-stu-id="e8baa-116">**Description**</span></span> | <span data-ttu-id="e8baa-117">En beskrivning av panelen.</span><span class="sxs-lookup"><span data-stu-id="e8baa-117">A description of the tile.</span></span> |
   | <span data-ttu-id="e8baa-118">**Internet-adress**</span><span class="sxs-lookup"><span data-stu-id="e8baa-118">**Internet address**</span></span> | <span data-ttu-id="e8baa-119">Ange URL-adressen till sidan för medarbetarens självbetjäningstjänster.</span><span class="sxs-lookup"><span data-stu-id="e8baa-119">Enter the URL to the employee self service page.</span></span> |
   | <span data-ttu-id="e8baa-120">**Panelstorlek**</span><span class="sxs-lookup"><span data-stu-id="e8baa-120">**Tile size**</span></span> | <span data-ttu-id="e8baa-121">Panelens storlek: liten, medium eller stor.</span><span class="sxs-lookup"><span data-stu-id="e8baa-121">The size of the tile: Small, Medium, or Large.</span></span> |
   | <span data-ttu-id="e8baa-122">**Mål**</span><span class="sxs-lookup"><span data-stu-id="e8baa-122">**Target**</span></span> | <span data-ttu-id="e8baa-123">Anger om sidan ska öppnas i ett nytt fönster eller i det aktuella fönstret.</span><span class="sxs-lookup"><span data-stu-id="e8baa-123">Specifies whether the page should open in a new window or the current window.</span></span> |
   | <span data-ttu-id="e8baa-124">**Bakgrundsbild för panel**</span><span class="sxs-lookup"><span data-stu-id="e8baa-124">**Tile background image**</span></span> | <span data-ttu-id="e8baa-125">URL till den bild som ska användas för panelen (valfritt).</span><span class="sxs-lookup"><span data-stu-id="e8baa-125">The URL of the image to use for the tile (optional).</span></span> |
   | <span data-ttu-id="e8baa-126">**Start**</span><span class="sxs-lookup"><span data-stu-id="e8baa-126">**Start**</span></span> | <span data-ttu-id="e8baa-127">Startdatum och tid som panelen ska vara tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="e8baa-127">The beginning date and time the tile should be available.</span></span> |
   | <span data-ttu-id="e8baa-128">**Slutdatum**</span><span class="sxs-lookup"><span data-stu-id="e8baa-128">**End**</span></span> | <span data-ttu-id="e8baa-129">Slutdatum och tid som panelen ska vara tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="e8baa-129">The end date and time the tile should be available.</span></span> |

4. <span data-ttu-id="e8baa-130">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="e8baa-130">Select **Save**.</span></span>

## <a name="set-up-a-flex-credit-plan-tile"></a><span data-ttu-id="e8baa-131">Inställning av panel för flexkreditplan</span><span class="sxs-lookup"><span data-stu-id="e8baa-131">Set up a flex credit plan tile</span></span>

1. <span data-ttu-id="e8baa-132">I arbetsytan **Förmånshantering** under **inställningar**, välj **Medarbetarens självbetjäningsparametrar**.</span><span class="sxs-lookup"><span data-stu-id="e8baa-132">In the **Benefits management** workspace, under **Setup**, select **Employee self service parameters**.</span></span>

2. <span data-ttu-id="e8baa-133">Välj fliken **Inställning av panel för flexkreditplan** och välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="e8baa-133">Select the **Flex credit plan tile setup** tab, and then select **New**.</span></span>

3. <span data-ttu-id="e8baa-134">Ange värden för de följande fälten:</span><span class="sxs-lookup"><span data-stu-id="e8baa-134">Specify values for the following fields:</span></span>

   | <span data-ttu-id="e8baa-135">Fält</span><span class="sxs-lookup"><span data-stu-id="e8baa-135">Field</span></span> | <span data-ttu-id="e8baa-136">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="e8baa-136">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="e8baa-137">**Panel-ID**</span><span class="sxs-lookup"><span data-stu-id="e8baa-137">**Tile ID**</span></span> | <span data-ttu-id="e8baa-138">Unik identifierare för panelen.</span><span class="sxs-lookup"><span data-stu-id="e8baa-138">The unique identifier for the tile.</span></span> |
   | <span data-ttu-id="e8baa-139">**Etikettext för panel**</span><span class="sxs-lookup"><span data-stu-id="e8baa-139">**Tile label text**</span></span> | <span data-ttu-id="e8baa-140">Texten som visas för panelen på självbetjäning.</span><span class="sxs-lookup"><span data-stu-id="e8baa-140">The text that will appear for the tile on Self service.</span></span> |
   | <span data-ttu-id="e8baa-141">**Beskrivning**</span><span class="sxs-lookup"><span data-stu-id="e8baa-141">**Description**</span></span> | <span data-ttu-id="e8baa-142">En beskrivning av panelen.</span><span class="sxs-lookup"><span data-stu-id="e8baa-142">A description of the tile.</span></span> |
   | <span data-ttu-id="e8baa-143">**Internet-adress**</span><span class="sxs-lookup"><span data-stu-id="e8baa-143">**Internet address**</span></span> | <span data-ttu-id="e8baa-144">Ange URL-adressen till sidan för medarbetarens självbetjäningstjänster.</span><span class="sxs-lookup"><span data-stu-id="e8baa-144">Enter the URL to the employee self service page.</span></span> |
   | <span data-ttu-id="e8baa-145">**Panelstorlek**</span><span class="sxs-lookup"><span data-stu-id="e8baa-145">**Tile size**</span></span> | <span data-ttu-id="e8baa-146">Panelens storlek: liten, medium eller stor.</span><span class="sxs-lookup"><span data-stu-id="e8baa-146">The size of the tile: Small, Medium, or Large.</span></span> |
   | <span data-ttu-id="e8baa-147">**Mål**</span><span class="sxs-lookup"><span data-stu-id="e8baa-147">**Target**</span></span> | <span data-ttu-id="e8baa-148">Anger om sidan ska öppnas i ett nytt fönster eller i det aktuella fönstret.</span><span class="sxs-lookup"><span data-stu-id="e8baa-148">Specifies whether the page should open in a new window or the current window.</span></span> |
   | <span data-ttu-id="e8baa-149">**Bakgrundsbild för panel**</span><span class="sxs-lookup"><span data-stu-id="e8baa-149">**Tile background image**</span></span> | <span data-ttu-id="e8baa-150">URL till den bild som ska användas för panelen (valfritt).</span><span class="sxs-lookup"><span data-stu-id="e8baa-150">The URL of the image to use for the tile (optional).</span></span> |
   | <span data-ttu-id="e8baa-151">**Start**</span><span class="sxs-lookup"><span data-stu-id="e8baa-151">**Start**</span></span> | <span data-ttu-id="e8baa-152">Startdatum och tid som panelen ska vara tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="e8baa-152">The beginning date and time the tile should be available.</span></span> |
   | <span data-ttu-id="e8baa-153">**Slutdatum**</span><span class="sxs-lookup"><span data-stu-id="e8baa-153">**End**</span></span> | <span data-ttu-id="e8baa-154">Slutdatum och tid som panelen ska vara tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="e8baa-154">The end date and time the tile should be available.</span></span> |

4. <span data-ttu-id="e8baa-155">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="e8baa-155">Select **Save**.</span></span>
