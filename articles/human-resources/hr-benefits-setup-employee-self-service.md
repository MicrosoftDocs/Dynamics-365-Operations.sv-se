---
title: Konfigurera självbetjäning för medarbetare
description: I Microsoft Dynamics 365 Human Resources kan du konfigurera paneler för navigering på högsta nivå i Självbetjäning för medarbetare.
author: andreabichsel
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 3e763a09e0a0f13eb7222a6ffbcb31b6230b83f4
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5797946"
---
# <a name="configure-employee-self-service"></a><span data-ttu-id="d634e-103">Konfigurera självbetjäning för medarbetare</span><span class="sxs-lookup"><span data-stu-id="d634e-103">Configure employee self service</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="d634e-104">I Microsoft Dynamics 365 Human Resources kan du konfigurera paneler för navigering på högsta nivå i Självbetjäning för medarbetare.</span><span class="sxs-lookup"><span data-stu-id="d634e-104">In Microsoft Dynamics 365 Human Resources, you can configure tiles for top-level navigation in Employee self service.</span></span> <span data-ttu-id="d634e-105">Paneler för förmånsplaner dirigerar användare till förmånsplaner som de berättigar till.</span><span class="sxs-lookup"><span data-stu-id="d634e-105">Benefit plan tiles direct users to benefit plans that they're eligible for.</span></span>

## <a name="set-up-a-benefit-plans-tile"></a><span data-ttu-id="d634e-106">Ställa in panel för förmånsplan</span><span class="sxs-lookup"><span data-stu-id="d634e-106">Set up a benefit plans tile</span></span>

1. <span data-ttu-id="d634e-107">I arbetsytan **Förmånshantering** under **inställningar**, välj **Medarbetarens självbetjäningsparametrar**.</span><span class="sxs-lookup"><span data-stu-id="d634e-107">In the **Benefits management** workspace, under **Setup**, select **Employee self service parameters**.</span></span>

2. <span data-ttu-id="d634e-108">Välj fliken **Inställning av paneler för förmånsplaner** och välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="d634e-108">Select the **Benefit plans tile setup** tab, and then select **New**.</span></span>

3. <span data-ttu-id="d634e-109">Ange värden för de följande fälten:</span><span class="sxs-lookup"><span data-stu-id="d634e-109">Specify values for the following fields:</span></span>

   | <span data-ttu-id="d634e-110">Fält</span><span class="sxs-lookup"><span data-stu-id="d634e-110">Field</span></span> | <span data-ttu-id="d634e-111">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="d634e-111">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="d634e-112">**Panel-ID**</span><span class="sxs-lookup"><span data-stu-id="d634e-112">**Tile ID**</span></span> | <span data-ttu-id="d634e-113">Unik identifierare för panelen.</span><span class="sxs-lookup"><span data-stu-id="d634e-113">The unique identifier for the tile.</span></span> |
   | <span data-ttu-id="d634e-114">**Etikettext för panel**</span><span class="sxs-lookup"><span data-stu-id="d634e-114">**Tile label text**</span></span> | <span data-ttu-id="d634e-115">Texten som visas för panelen på självbetjäning.</span><span class="sxs-lookup"><span data-stu-id="d634e-115">The text that will appear for the tile on Self-service.</span></span> |
   | <span data-ttu-id="d634e-116">**Beskrivning**</span><span class="sxs-lookup"><span data-stu-id="d634e-116">**Description**</span></span> | <span data-ttu-id="d634e-117">En beskrivning av panelen.</span><span class="sxs-lookup"><span data-stu-id="d634e-117">A description of the tile.</span></span> |
   | <span data-ttu-id="d634e-118">**Internet-adress**</span><span class="sxs-lookup"><span data-stu-id="d634e-118">**Internet address**</span></span> | <span data-ttu-id="d634e-119">Ange URL-adressen till sidan för medarbetarens självbetjäningstjänster.</span><span class="sxs-lookup"><span data-stu-id="d634e-119">Enter the URL to the employee self service page.</span></span> |
   | <span data-ttu-id="d634e-120">**Panelstorlek**</span><span class="sxs-lookup"><span data-stu-id="d634e-120">**Tile size**</span></span> | <span data-ttu-id="d634e-121">Panelens storlek: liten, medium eller stor.</span><span class="sxs-lookup"><span data-stu-id="d634e-121">The size of the tile: Small, Medium, or Large.</span></span> |
   | <span data-ttu-id="d634e-122">**Mål**</span><span class="sxs-lookup"><span data-stu-id="d634e-122">**Target**</span></span> | <span data-ttu-id="d634e-123">Anger om sidan ska öppnas i ett nytt fönster eller i det aktuella fönstret.</span><span class="sxs-lookup"><span data-stu-id="d634e-123">Specifies whether the page should open in a new window or the current window.</span></span> |
   | <span data-ttu-id="d634e-124">**Bakgrundsbild för panel**</span><span class="sxs-lookup"><span data-stu-id="d634e-124">**Tile background image**</span></span> | <span data-ttu-id="d634e-125">URL till den bild som ska användas för panelen (valfritt).</span><span class="sxs-lookup"><span data-stu-id="d634e-125">The URL of the image to use for the tile (optional).</span></span> |
   | <span data-ttu-id="d634e-126">**Start**</span><span class="sxs-lookup"><span data-stu-id="d634e-126">**Start**</span></span> | <span data-ttu-id="d634e-127">Startdatum och tid som panelen ska vara tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="d634e-127">The beginning date and time the tile should be available.</span></span> |
   | <span data-ttu-id="d634e-128">**Slutdatum**</span><span class="sxs-lookup"><span data-stu-id="d634e-128">**End**</span></span> | <span data-ttu-id="d634e-129">Slutdatum och tid som panelen ska vara tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="d634e-129">The end date and time the tile should be available.</span></span> |

4. <span data-ttu-id="d634e-130">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="d634e-130">Select **Save**.</span></span>

## <a name="set-up-a-flex-credit-plan-tile"></a><span data-ttu-id="d634e-131">Inställning av panel för flexkreditplan</span><span class="sxs-lookup"><span data-stu-id="d634e-131">Set up a flex credit plan tile</span></span>

1. <span data-ttu-id="d634e-132">I arbetsytan **Förmånshantering** under **inställningar**, välj **Medarbetarens självbetjäningsparametrar**.</span><span class="sxs-lookup"><span data-stu-id="d634e-132">In the **Benefits management** workspace, under **Setup**, select **Employee self service parameters**.</span></span>

2. <span data-ttu-id="d634e-133">Välj fliken **Inställning av panel för flexkreditplan** och välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="d634e-133">Select the **Flex credit plan tile setup** tab, and then select **New**.</span></span>

3. <span data-ttu-id="d634e-134">Ange värden för de följande fälten:</span><span class="sxs-lookup"><span data-stu-id="d634e-134">Specify values for the following fields:</span></span>

   | <span data-ttu-id="d634e-135">Fält</span><span class="sxs-lookup"><span data-stu-id="d634e-135">Field</span></span> | <span data-ttu-id="d634e-136">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="d634e-136">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="d634e-137">**Panel-ID**</span><span class="sxs-lookup"><span data-stu-id="d634e-137">**Tile ID**</span></span> | <span data-ttu-id="d634e-138">Unik identifierare för panelen.</span><span class="sxs-lookup"><span data-stu-id="d634e-138">The unique identifier for the tile.</span></span> |
   | <span data-ttu-id="d634e-139">**Etikettext för panel**</span><span class="sxs-lookup"><span data-stu-id="d634e-139">**Tile label text**</span></span> | <span data-ttu-id="d634e-140">Texten som visas för panelen på självbetjäning.</span><span class="sxs-lookup"><span data-stu-id="d634e-140">The text that will appear for the tile on Self service.</span></span> |
   | <span data-ttu-id="d634e-141">**Beskrivning**</span><span class="sxs-lookup"><span data-stu-id="d634e-141">**Description**</span></span> | <span data-ttu-id="d634e-142">En beskrivning av panelen.</span><span class="sxs-lookup"><span data-stu-id="d634e-142">A description of the tile.</span></span> |
   | <span data-ttu-id="d634e-143">**Internet-adress**</span><span class="sxs-lookup"><span data-stu-id="d634e-143">**Internet address**</span></span> | <span data-ttu-id="d634e-144">Ange URL-adressen till sidan för medarbetarens självbetjäningstjänster.</span><span class="sxs-lookup"><span data-stu-id="d634e-144">Enter the URL to the employee self service page.</span></span> |
   | <span data-ttu-id="d634e-145">**Panelstorlek**</span><span class="sxs-lookup"><span data-stu-id="d634e-145">**Tile size**</span></span> | <span data-ttu-id="d634e-146">Panelens storlek: liten, medium eller stor.</span><span class="sxs-lookup"><span data-stu-id="d634e-146">The size of the tile: Small, Medium, or Large.</span></span> |
   | <span data-ttu-id="d634e-147">**Mål**</span><span class="sxs-lookup"><span data-stu-id="d634e-147">**Target**</span></span> | <span data-ttu-id="d634e-148">Anger om sidan ska öppnas i ett nytt fönster eller i det aktuella fönstret.</span><span class="sxs-lookup"><span data-stu-id="d634e-148">Specifies whether the page should open in a new window or the current window.</span></span> |
   | <span data-ttu-id="d634e-149">**Bakgrundsbild för panel**</span><span class="sxs-lookup"><span data-stu-id="d634e-149">**Tile background image**</span></span> | <span data-ttu-id="d634e-150">URL till den bild som ska användas för panelen (valfritt).</span><span class="sxs-lookup"><span data-stu-id="d634e-150">The URL of the image to use for the tile (optional).</span></span> |
   | <span data-ttu-id="d634e-151">**Start**</span><span class="sxs-lookup"><span data-stu-id="d634e-151">**Start**</span></span> | <span data-ttu-id="d634e-152">Startdatum och tid som panelen ska vara tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="d634e-152">The beginning date and time the tile should be available.</span></span> |
   | <span data-ttu-id="d634e-153">**Slutdatum**</span><span class="sxs-lookup"><span data-stu-id="d634e-153">**End**</span></span> | <span data-ttu-id="d634e-154">Slutdatum och tid som panelen ska vara tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="d634e-154">The end date and time the tile should be available.</span></span> |

4. <span data-ttu-id="d634e-155">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="d634e-155">Select **Save**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]