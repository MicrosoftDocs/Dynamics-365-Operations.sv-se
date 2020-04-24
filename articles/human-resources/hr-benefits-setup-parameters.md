---
title: Ställ in parametrar för hantering av förmåner
description: Konfigurera parametrar för förmånshantering i Microsoft Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 9d6d463df08b9ae68047f09316f19e98740a8441
ms.sourcegitcommit: a9461650d11d6845e1942865ebf7e35f75f61ad3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/06/2020
ms.locfileid: "3229773"
---
# <a name="set-benefits-management-parameters"></a><span data-ttu-id="f4d60-103">Ställa in parametrar för förmånshantering</span><span class="sxs-lookup"><span data-stu-id="f4d60-103">Set Benefits management parameters</span></span>

<span data-ttu-id="f4d60-104">Innan du kan ställa in tjänstledighetsplaner i Microsoft Dynamics 365 Human Resources måste du konfigurera parametrar för hantering av förmåner.</span><span class="sxs-lookup"><span data-stu-id="f4d60-104">Before you can set up leave plans in Microsoft Dynamics 365 Human Resources, you must configure Benefits management parameters.</span></span> <span data-ttu-id="f4d60-105">Dessa parametrar ställer in standardvärden, orsakskoder och andra alternativ.</span><span class="sxs-lookup"><span data-stu-id="f4d60-105">These parameters set default values, reason codes, and other options.</span></span>

## <a name="configure-general-parameters"></a><span data-ttu-id="f4d60-106">Konfigurera allmänna parametrar</span><span class="sxs-lookup"><span data-stu-id="f4d60-106">Configure general parameters</span></span>

1. <span data-ttu-id="f4d60-107">I arbetsytan **Förmånshantering** under **inställningar**, välj **parametrar**.</span><span class="sxs-lookup"><span data-stu-id="f4d60-107">In the **Benefits management** workspace, under **Setup**, select **Parameters**.</span></span>

2. <span data-ttu-id="f4d60-108">På fliken **Allmänt**, ange värden för följande fält:</span><span class="sxs-lookup"><span data-stu-id="f4d60-108">In the **General** tab, specify values for the following fields:</span></span>

   | <span data-ttu-id="f4d60-109">Fält</span><span class="sxs-lookup"><span data-stu-id="f4d60-109">Field</span></span> | <span data-ttu-id="f4d60-110">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="f4d60-110">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="f4d60-111">**Land/region**</span><span class="sxs-lookup"><span data-stu-id="f4d60-111">**Country/region**</span></span> | <span data-ttu-id="f4d60-112">Fältet **land/region** bestämmer visningsordningen för postnummer och stater.</span><span class="sxs-lookup"><span data-stu-id="f4d60-112">The **Country/region** field determines the display order of ZIP codes/states.</span></span> <span data-ttu-id="f4d60-113">Det valda landet visas först i den nedrullningsbara listan.</span><span class="sxs-lookup"><span data-stu-id="f4d60-113">The selected country displays first in the dropdown list.</span></span> |
   | <span data-ttu-id="f4d60-114">**Orsakskod för anmälan**</span><span class="sxs-lookup"><span data-stu-id="f4d60-114">**Enrollment reason code**</span></span> | <span data-ttu-id="f4d60-115">Välj en standardorsakskod som ska användas när medarbetares planer skapas när du öppnar registreringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="f4d60-115">Select a default reason code to use when employee plans are created during open enrollment processing.</span></span> |
   | <span data-ttu-id="f4d60-116">**Orsakskod för annullering**</span><span class="sxs-lookup"><span data-stu-id="f4d60-116">**Cancellation reason code**</span></span> | <span data-ttu-id="f4d60-117">Orsakskoden som ska användas när en förmånsplanen för medarbetare annulleras.</span><span class="sxs-lookup"><span data-stu-id="f4d60-117">The reason code to use when an employee benefit plan is canceled.</span></span> <span data-ttu-id="f4d60-118">Den visas i en dialogruta under annulleringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="f4d60-118">It displays in a dialog during the cancellation process.</span></span> <span data-ttu-id="f4d60-119">Användare kan ändra **Orsakskod för annullering** vid behov.</span><span class="sxs-lookup"><span data-stu-id="f4d60-119">Users can change it the **Cancellation reason code** if necessary.</span></span> |
   | <span data-ttu-id="f4d60-120">**Öppna orsakskod igen**</span><span class="sxs-lookup"><span data-stu-id="f4d60-120">**Reopen reason code**</span></span> | <span data-ttu-id="f4d60-121">Orsakskoden som ska användas när en förmånsplanen för medarbetare öppnas igen.</span><span class="sxs-lookup"><span data-stu-id="f4d60-121">The reason code to use when an employee benefit plan is reopened.</span></span> <span data-ttu-id="f4d60-122">Den visas i en dialogruta under annulleringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="f4d60-122">It displays in a dialog during the cancellation process.</span></span> <span data-ttu-id="f4d60-123">Användare kan ändra **Orsakskod för öppnas igen** vid behov.</span><span class="sxs-lookup"><span data-stu-id="f4d60-123">Users can change the **Reopen reason code** if necessary.</span></span> | 
   | <span data-ttu-id="f4d60-124">**Orsakskod för livshändelse**</span><span class="sxs-lookup"><span data-stu-id="f4d60-124">**Life event reason code**</span></span> | <span data-ttu-id="f4d60-125">Orsakskoden som ska användas när en livshändelse inträffar.</span><span class="sxs-lookup"><span data-stu-id="f4d60-125">The reason code to use when a life event occurs.</span></span> |
   | <span data-ttu-id="f4d60-126">**Orsakskod för prisändring**</span><span class="sxs-lookup"><span data-stu-id="f4d60-126">**Rate change reason code**</span></span> | <span data-ttu-id="f4d60-127">Orsakskoden som ska användas vid annullering och öppnande av en förmånsplan för medarbetare under uppdateringsprocessen av prisändringen.</span><span class="sxs-lookup"><span data-stu-id="f4d60-127">The reason code to use when canceling and reopening an employee benefit plan during the rate change update process.</span></span> <span data-ttu-id="f4d60-128">Den visar vilka poster som ändrades under uppdatering av prisändring.</span><span class="sxs-lookup"><span data-stu-id="f4d60-128">It indicates which records were changed by the rate change update process.</span></span> |
   | <span data-ttu-id="f4d60-129">**Berättigad till nyanställning**</span><span class="sxs-lookup"><span data-stu-id="f4d60-129">**New hire eligible**</span></span> | <span data-ttu-id="f4d60-130">Anger om nya anställningar är berättigade.</span><span class="sxs-lookup"><span data-stu-id="f4d60-130">Specifies whether new hires are eligible.</span></span> |
   | <span data-ttu-id="f4d60-131">**Period för ny anställningsanmälan**</span><span class="sxs-lookup"><span data-stu-id="f4d60-131">**New hire enrollment period**</span></span> | <span data-ttu-id="f4d60-132">Den tidsperiod då den nya anställningsanmälan är tillåten.</span><span class="sxs-lookup"><span data-stu-id="f4d60-132">The period of time the new hire enrollment is allowed.</span></span></br></br><span data-ttu-id="f4d60-133">**Obs**! den här inställningen åsidosätter eventuella nya anställningsperioder för anställningsanmälan som du ställer in i berättiganderegler för planen.</span><span class="sxs-lookup"><span data-stu-id="f4d60-133">**Note**: This setting overrides any new hire enrollment period you set on the plan eligibility rule.</span></span> | 
   | <span data-ttu-id="f4d60-134">**Livshändelser har aktiverats**</span><span class="sxs-lookup"><span data-stu-id="f4d60-134">**Life events enabled**</span></span> | <span data-ttu-id="f4d60-135">Aktiverar livshändelser.</span><span class="sxs-lookup"><span data-stu-id="f4d60-135">Enables life events.</span></span> |
   | <span data-ttu-id="f4d60-136">**Dölj formulären för tidigare förmåner**</span><span class="sxs-lookup"><span data-stu-id="f4d60-136">**Hide legacy benefit forms**</span></span> | <span data-ttu-id="f4d60-137">Gör att du kan dölja äldre förmånsformulär.</span><span class="sxs-lookup"><span data-stu-id="f4d60-137">Allows you to hide legacy benefit forms.</span></span> |

3. <span data-ttu-id="f4d60-138">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="f4d60-138">Select **Save**.</span></span>

## <a name="configure-employee-self-service-parameters"></a><span data-ttu-id="f4d60-139">Konfigurera anställdas självbetjäningsparametrar</span><span class="sxs-lookup"><span data-stu-id="f4d60-139">Configure Employee self service parameters</span></span>

1. <span data-ttu-id="f4d60-140">I arbetsytan **Förmånshantering** under **inställningar**, välj **parametrar**.</span><span class="sxs-lookup"><span data-stu-id="f4d60-140">In the **Benefits management** workspace, under **Setup**, select **Parameters**.</span></span>

2. <span data-ttu-id="f4d60-141">På fliken **Självbetjäning för medarbetare** ange värden för följande fält:</span><span class="sxs-lookup"><span data-stu-id="f4d60-141">In the **Employee self service** tab, specify values for the following fields:</span></span>

   | <span data-ttu-id="f4d60-142">Fält</span><span class="sxs-lookup"><span data-stu-id="f4d60-142">Field</span></span> | <span data-ttu-id="f4d60-143">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="f4d60-143">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="f4d60-144">**Förmånsverifiering**</span><span class="sxs-lookup"><span data-stu-id="f4d60-144">**Benefit verification**</span></span> | <span data-ttu-id="f4d60-145">Verifieringstext under utcheckningen från självbetjäningen för förmåner.</span><span class="sxs-lookup"><span data-stu-id="f4d60-145">The verification text to use during self-service benefits checkout.</span></span> |
   | <span data-ttu-id="f4d60-146">**Välj befullmäktigade automatiskt**</span><span class="sxs-lookup"><span data-stu-id="f4d60-146">**Auto select designees**</span></span> | <span data-ttu-id="f4d60-147">Anger om man automatiskt ska välja beroende och stödmottagare baserat på deras berättigande till planalternativ.</span><span class="sxs-lookup"><span data-stu-id="f4d60-147">Specifies whether to automatically select dependents and beneficiaries based on their eligibility for plan options.</span></span> |

3. <span data-ttu-id="f4d60-148">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="f4d60-148">Select **Save**.</span></span>
