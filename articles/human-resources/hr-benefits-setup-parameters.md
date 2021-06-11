---
title: Ställa in förmånshantering och medarbetarnas självbetjäningsparametrar för alla företag
description: Konfigurera parametrar för förmånshantering och medarbetarnas självbetjäning i Microsoft Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 12/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d668238378e41287c7a9f845ae3e67078fc7776a
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/18/2021
ms.locfileid: "6058978"
---
# <a name="set-benefits-management-and-employee-self-service-parameters-for-all-companies"></a><span data-ttu-id="13b56-103">Ställa in förmånshantering och medarbetarnas självbetjäningsparametrar för alla företag</span><span class="sxs-lookup"><span data-stu-id="13b56-103">Set Benefits management and Employee self-service parameters for all companies</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="13b56-104">Innan du kan konfigurera förmånsplaner i Microsoft Dynamics 365 Human Resources måste du konfigurera parametrar för hantering av förmåner.</span><span class="sxs-lookup"><span data-stu-id="13b56-104">Before you can set up benefit plans in Microsoft Dynamics 365 Human Resources, you must configure Benefits management parameters.</span></span> <span data-ttu-id="13b56-105">Dessa parametrar ställer in standardvärden, orsakskoder och andra alternativ.</span><span class="sxs-lookup"><span data-stu-id="13b56-105">These parameters set default values, reason codes, and other options.</span></span> 

## <a name="configure-general-parameters"></a><span data-ttu-id="13b56-106">Konfigurera allmänna parametrar</span><span class="sxs-lookup"><span data-stu-id="13b56-106">Configure general parameters</span></span>

1. <span data-ttu-id="13b56-107">I arbetsytan **Förmånshantering** under **inställningar**, välj **Dela personalparametrar**.</span><span class="sxs-lookup"><span data-stu-id="13b56-107">In the **Benefits management** workspace, under **Setup**, select **Human Resources Shared Parameters**.</span></span>

2. <span data-ttu-id="13b56-108">På fliken **Hantering av förmåner**, ange värden för följande fält:</span><span class="sxs-lookup"><span data-stu-id="13b56-108">In the **Benefits management** tab, specify values for the following fields:</span></span>

   | <span data-ttu-id="13b56-109">Fält</span><span class="sxs-lookup"><span data-stu-id="13b56-109">Field</span></span> | <span data-ttu-id="13b56-110">beskrivning</span><span class="sxs-lookup"><span data-stu-id="13b56-110">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="13b56-111">**Land/region**</span><span class="sxs-lookup"><span data-stu-id="13b56-111">**Country/region**</span></span> | <span data-ttu-id="13b56-112">Fältet **land/region** bestämmer visningsordningen för postnummer och stater.</span><span class="sxs-lookup"><span data-stu-id="13b56-112">The **Country/region** field determines the display order of ZIP codes/states.</span></span> <span data-ttu-id="13b56-113">Det valda landet visas först i den nedrullningsbara listan.</span><span class="sxs-lookup"><span data-stu-id="13b56-113">The selected country displays first in the dropdown list.</span></span> |
   | <span data-ttu-id="13b56-114">**Orsakskod för anmälan**</span><span class="sxs-lookup"><span data-stu-id="13b56-114">**Enrollment reason code**</span></span> | <span data-ttu-id="13b56-115">Välj en standardorsakskod som ska användas när medarbetares planer skapas när du öppnar registreringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="13b56-115">Select a default reason code to use when employee plans are created during open enrollment processing.</span></span> |
   | <span data-ttu-id="13b56-116">**Orsakskod för annullering**</span><span class="sxs-lookup"><span data-stu-id="13b56-116">**Cancellation reason code**</span></span> | <span data-ttu-id="13b56-117">Orsakskoden som ska användas när en förmånsplanen för medarbetare annulleras.</span><span class="sxs-lookup"><span data-stu-id="13b56-117">The reason code to use when an employee benefit plan is canceled.</span></span> <span data-ttu-id="13b56-118">Den visas i en dialogruta under annulleringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="13b56-118">It displays in a dialog during the cancellation process.</span></span> <span data-ttu-id="13b56-119">Användare kan ändra **Orsakskod för annullering** vid behov.</span><span class="sxs-lookup"><span data-stu-id="13b56-119">Users can change it the **Cancellation reason code** if necessary.</span></span> |
   | <span data-ttu-id="13b56-120">**Öppna orsakskod igen**</span><span class="sxs-lookup"><span data-stu-id="13b56-120">**Reopen reason code**</span></span> | <span data-ttu-id="13b56-121">Orsakskoden som ska användas när en förmånsplanen för medarbetare öppnas igen.</span><span class="sxs-lookup"><span data-stu-id="13b56-121">The reason code to use when an employee benefit plan is reopened.</span></span> <span data-ttu-id="13b56-122">Den visas i en dialogruta under annulleringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="13b56-122">It displays in a dialog during the cancellation process.</span></span> <span data-ttu-id="13b56-123">Användare kan ändra **Orsakskod för öppnas igen** vid behov.</span><span class="sxs-lookup"><span data-stu-id="13b56-123">Users can change the **Reopen reason code** if necessary.</span></span> | 
   | <span data-ttu-id="13b56-124">**Orsakskod för livshändelse**</span><span class="sxs-lookup"><span data-stu-id="13b56-124">**Life event reason code**</span></span> | <span data-ttu-id="13b56-125">Orsakskoden som ska användas när en livshändelse inträffar.</span><span class="sxs-lookup"><span data-stu-id="13b56-125">The reason code to use when a life event occurs.</span></span> |
   | <span data-ttu-id="13b56-126">**Orsakskod för prisändring**</span><span class="sxs-lookup"><span data-stu-id="13b56-126">**Rate change reason code**</span></span> | <span data-ttu-id="13b56-127">Orsakskoden som ska användas vid annullering och öppnande av en förmånsplan för medarbetare under uppdateringsprocessen av prisändringen.</span><span class="sxs-lookup"><span data-stu-id="13b56-127">The reason code to use when canceling and reopening an employee benefit plan during the rate change update process.</span></span> <span data-ttu-id="13b56-128">Den visar vilka poster som ändrades under uppdatering av prisändring.</span><span class="sxs-lookup"><span data-stu-id="13b56-128">It indicates which records were changed by the rate change update process.</span></span> |
   | <span data-ttu-id="13b56-129">**Årlig inkomst av förmåner**</span><span class="sxs-lookup"><span data-stu-id="13b56-129">**Benefits annual salary**</span></span> | <span data-ttu-id="13b56-130">Gör att du kan ställa in ett belopp för **Årslön** för en medarbetare.</span><span class="sxs-lookup"><span data-stu-id="13b56-130">Enables you to set a **Benefits annual salary** amount for an employee.</span></span> <span data-ttu-id="13b56-131">Personal kommer att använda beloppet **Årslön** vid fastställande av täckningsbelopp, istället för det årliga beloppet för fast ersättning.</span><span class="sxs-lookup"><span data-stu-id="13b56-131">Human Resources will use the **Benefits annual salary** amount when determining coverage amounts, instead of the fixed compensation annual amount.</span></span> |
   | <span data-ttu-id="13b56-132">**Berättigad till nyanställning**</span><span class="sxs-lookup"><span data-stu-id="13b56-132">**New hire eligible**</span></span> | <span data-ttu-id="13b56-133">Anger om nya anställningar är berättigade.</span><span class="sxs-lookup"><span data-stu-id="13b56-133">Specifies whether new hires are eligible.</span></span> |
   | <span data-ttu-id="13b56-134">**Period för ny anställningsanmälan**</span><span class="sxs-lookup"><span data-stu-id="13b56-134">**New hire enrollment period**</span></span> | <span data-ttu-id="13b56-135">Den tidsperiod då den nya anställningsanmälan är tillåten.</span><span class="sxs-lookup"><span data-stu-id="13b56-135">The period of time the new hire enrollment is allowed.</span></span></br></br><span data-ttu-id="13b56-136">**Obs**! den här inställningen åsidosätter eventuella nya anställningsperioder för anställningsanmälan som du ställer in i berättiganderegler för planen.</span><span class="sxs-lookup"><span data-stu-id="13b56-136">**Note**: This setting overrides any new hire enrollment period you set on the plan eligibility rule.</span></span> |
   | <span data-ttu-id="13b56-137">**Standardvärde för lönefrekvens**</span><span class="sxs-lookup"><span data-stu-id="13b56-137">**Default pay frequency**</span></span> | <span data-ttu-id="13b56-138">Standard lönefrekvensen som används när nya arbetare läggs till.</span><span class="sxs-lookup"><span data-stu-id="13b56-138">The default pay frequency to use when new workers are added.</span></span> |
   | <span data-ttu-id="13b56-139">**Livshändelser har aktiverats**</span><span class="sxs-lookup"><span data-stu-id="13b56-139">**Life events enabled**</span></span> | <span data-ttu-id="13b56-140">Aktiverar livshändelser.</span><span class="sxs-lookup"><span data-stu-id="13b56-140">Enables life events.</span></span> |
   | <span data-ttu-id="13b56-141">**Dölj formulären för tidigare förmåner**</span><span class="sxs-lookup"><span data-stu-id="13b56-141">**Hide legacy benefit forms**</span></span> | <span data-ttu-id="13b56-142">Gör att du kan dölja äldre förmånsformulär.</span><span class="sxs-lookup"><span data-stu-id="13b56-142">Allows you to hide legacy benefit forms.</span></span> |
   | <span data-ttu-id="13b56-143">**Förmånsverifiering**</span><span class="sxs-lookup"><span data-stu-id="13b56-143">**Benefit verification**</span></span> | <span data-ttu-id="13b56-144">Den verifieringstext som ska användas i samband med självbetjäningsutcheckning av förmåner.</span><span class="sxs-lookup"><span data-stu-id="13b56-144">The verification text to use during self-service benefits checkout.</span></span> |
   | <span data-ttu-id="13b56-145">**Välj befullmäktigade automatiskt**</span><span class="sxs-lookup"><span data-stu-id="13b56-145">**Auto select designees**</span></span> | <span data-ttu-id="13b56-146">Anger om man automatiskt ska välja beroende och stödmottagare baserat på deras berättigande till planalternativ.</span><span class="sxs-lookup"><span data-stu-id="13b56-146">Specifies whether to automatically select dependents and beneficiaries, based on their eligibility for plan options.</span></span> |

3. <span data-ttu-id="13b56-147">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="13b56-147">Select **Save**.</span></span>

## <a name="configure-employee-self-service-parameters"></a><span data-ttu-id="13b56-148">Konfigurera anställdas självbetjäningsparametrar</span><span class="sxs-lookup"><span data-stu-id="13b56-148">Configure Employee self-service parameters</span></span>

1. <span data-ttu-id="13b56-149">I arbetsytan **Förmånshantering** under **inställningar**, välj **Personalparametrar**.</span><span class="sxs-lookup"><span data-stu-id="13b56-149">In the **Benefits management** workspace, under **Setup**, select **Human Resources Parameters**.</span></span>

2. <span data-ttu-id="13b56-150">På fliken **Hantering av förmåner**, ange värden för följande fält:</span><span class="sxs-lookup"><span data-stu-id="13b56-150">In the **Benefits management** tab, specify values for the following fields:</span></span>

   | <span data-ttu-id="13b56-151">Fält</span><span class="sxs-lookup"><span data-stu-id="13b56-151">Field</span></span> | <span data-ttu-id="13b56-152">beskrivning</span><span class="sxs-lookup"><span data-stu-id="13b56-152">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="13b56-153">**Förmånsverifiering**</span><span class="sxs-lookup"><span data-stu-id="13b56-153">**Benefit verification**</span></span> | <span data-ttu-id="13b56-154">Den verifieringstext som ska användas i samband med självbetjäningsutcheckning av förmåner.</span><span class="sxs-lookup"><span data-stu-id="13b56-154">The verification text to use during self-service benefits checkout.</span></span> |
   | <span data-ttu-id="13b56-155">**Välj befullmäktigade automatiskt**</span><span class="sxs-lookup"><span data-stu-id="13b56-155">**Auto select designees**</span></span> | <span data-ttu-id="13b56-156">Anger om man automatiskt ska välja beroende och stödmottagare baserat på deras berättigande till planalternativ.</span><span class="sxs-lookup"><span data-stu-id="13b56-156">Specifies whether to automatically select dependents and beneficiaries based on their eligibility for plan options.</span></span> |

3. <span data-ttu-id="13b56-157">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="13b56-157">Select **Save**.</span></span>




[!INCLUDE[footer-include](../includes/footer-banner.md)]