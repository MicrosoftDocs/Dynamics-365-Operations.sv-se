---
title: Ställ in parametrar för hantering av förmåner
description: Konfigurera parametrar för förmånshantering i Microsoft Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 07/16/2020
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
ms.openlocfilehash: 85bbe5d3b422f2f29f1d1fe8ee269b407da691c2
ms.sourcegitcommit: 9dc5c7dd5877cc6e7cd0059d173bcd8052ba13bc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/16/2020
ms.locfileid: "3599366"
---
# <a name="set-benefits-management-parameters"></a><span data-ttu-id="9e41e-103">Ställa in parametrar för förmånshantering</span><span class="sxs-lookup"><span data-stu-id="9e41e-103">Set Benefits management parameters</span></span>

<span data-ttu-id="9e41e-104">Innan du kan ställa in tjänstledighetsplaner i Microsoft Dynamics 365 Human Resources måste du konfigurera parametrar för hantering av förmåner.</span><span class="sxs-lookup"><span data-stu-id="9e41e-104">Before you can set up leave plans in Microsoft Dynamics 365 Human Resources, you must configure Benefits management parameters.</span></span> <span data-ttu-id="9e41e-105">Dessa parametrar ställer in standardvärden, orsakskoder och andra alternativ.</span><span class="sxs-lookup"><span data-stu-id="9e41e-105">These parameters set default values, reason codes, and other options.</span></span>

## <a name="configure-general-parameters"></a><span data-ttu-id="9e41e-106">Konfigurera allmänna parametrar</span><span class="sxs-lookup"><span data-stu-id="9e41e-106">Configure general parameters</span></span>

1. <span data-ttu-id="9e41e-107">I arbetsytan **Förmånshantering** under **inställningar**, välj **Dela personalparametrar**.</span><span class="sxs-lookup"><span data-stu-id="9e41e-107">In the **Benefits management** workspace, under **Setup**, select **Human Resources Shared Parameters**.</span></span>

2. <span data-ttu-id="9e41e-108">På fliken **Allmänt**, ange värden för följande fält:</span><span class="sxs-lookup"><span data-stu-id="9e41e-108">In the **General** tab, specify values for the following fields:</span></span>

   | <span data-ttu-id="9e41e-109">Fält</span><span class="sxs-lookup"><span data-stu-id="9e41e-109">Field</span></span> | <span data-ttu-id="9e41e-110">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="9e41e-110">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="9e41e-111">**Land/region**</span><span class="sxs-lookup"><span data-stu-id="9e41e-111">**Country/region**</span></span> | <span data-ttu-id="9e41e-112">Fältet **land/region** bestämmer visningsordningen för postnummer och stater.</span><span class="sxs-lookup"><span data-stu-id="9e41e-112">The **Country/region** field determines the display order of ZIP codes/states.</span></span> <span data-ttu-id="9e41e-113">Det valda landet visas först i den nedrullningsbara listan.</span><span class="sxs-lookup"><span data-stu-id="9e41e-113">The selected country displays first in the dropdown list.</span></span> |
   | <span data-ttu-id="9e41e-114">**Orsakskod för anmälan**</span><span class="sxs-lookup"><span data-stu-id="9e41e-114">**Enrollment reason code**</span></span> | <span data-ttu-id="9e41e-115">Välj en standardorsakskod som ska användas när medarbetares planer skapas när du öppnar registreringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="9e41e-115">Select a default reason code to use when employee plans are created during open enrollment processing.</span></span> |
   | <span data-ttu-id="9e41e-116">**Orsakskod för annullering**</span><span class="sxs-lookup"><span data-stu-id="9e41e-116">**Cancellation reason code**</span></span> | <span data-ttu-id="9e41e-117">Orsakskoden som ska användas när en förmånsplanen för medarbetare annulleras.</span><span class="sxs-lookup"><span data-stu-id="9e41e-117">The reason code to use when an employee benefit plan is canceled.</span></span> <span data-ttu-id="9e41e-118">Den visas i en dialogruta under annulleringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="9e41e-118">It displays in a dialog during the cancellation process.</span></span> <span data-ttu-id="9e41e-119">Användare kan ändra **Orsakskod för annullering** vid behov.</span><span class="sxs-lookup"><span data-stu-id="9e41e-119">Users can change it the **Cancellation reason code** if necessary.</span></span> |
   | <span data-ttu-id="9e41e-120">**Öppna orsakskod igen**</span><span class="sxs-lookup"><span data-stu-id="9e41e-120">**Reopen reason code**</span></span> | <span data-ttu-id="9e41e-121">Orsakskoden som ska användas när en förmånsplanen för medarbetare öppnas igen.</span><span class="sxs-lookup"><span data-stu-id="9e41e-121">The reason code to use when an employee benefit plan is reopened.</span></span> <span data-ttu-id="9e41e-122">Den visas i en dialogruta under annulleringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="9e41e-122">It displays in a dialog during the cancellation process.</span></span> <span data-ttu-id="9e41e-123">Användare kan ändra **Orsakskod för öppnas igen** vid behov.</span><span class="sxs-lookup"><span data-stu-id="9e41e-123">Users can change the **Reopen reason code** if necessary.</span></span> | 
   | <span data-ttu-id="9e41e-124">**Orsakskod för livshändelse**</span><span class="sxs-lookup"><span data-stu-id="9e41e-124">**Life event reason code**</span></span> | <span data-ttu-id="9e41e-125">Orsakskoden som ska användas när en livshändelse inträffar.</span><span class="sxs-lookup"><span data-stu-id="9e41e-125">The reason code to use when a life event occurs.</span></span> |
   | <span data-ttu-id="9e41e-126">**Orsakskod för prisändring**</span><span class="sxs-lookup"><span data-stu-id="9e41e-126">**Rate change reason code**</span></span> | <span data-ttu-id="9e41e-127">Orsakskoden som ska användas vid annullering och öppnande av en förmånsplan för medarbetare under uppdateringsprocessen av prisändringen.</span><span class="sxs-lookup"><span data-stu-id="9e41e-127">The reason code to use when canceling and reopening an employee benefit plan during the rate change update process.</span></span> <span data-ttu-id="9e41e-128">Den visar vilka poster som ändrades under uppdatering av prisändring.</span><span class="sxs-lookup"><span data-stu-id="9e41e-128">It indicates which records were changed by the rate change update process.</span></span> |
   | <span data-ttu-id="9e41e-129">**Årlig inkomst av förmåner**</span><span class="sxs-lookup"><span data-stu-id="9e41e-129">**Benefits annual salary**</span></span> | <span data-ttu-id="9e41e-130">Gör att du kan ställa in ett belopp för **Årslön** för en medarbetare.</span><span class="sxs-lookup"><span data-stu-id="9e41e-130">Enables you to set a **Benefits annual salary** amount for an employee.</span></span> <span data-ttu-id="9e41e-131">Personal kommer att använda beloppet **Årslön** vid fastställande av täckningsbelopp, istället för det årliga beloppet för fast ersättning.</span><span class="sxs-lookup"><span data-stu-id="9e41e-131">Human Resources will use the **Benefits annual salary** amount when determing coverage amounts, instead of the fixed compensation annual amount.</span></span> |
   | <span data-ttu-id="9e41e-132">**Berättigad till nyanställning**</span><span class="sxs-lookup"><span data-stu-id="9e41e-132">**New hire eligible**</span></span> | <span data-ttu-id="9e41e-133">Anger om nya anställningar är berättigade.</span><span class="sxs-lookup"><span data-stu-id="9e41e-133">Specifies whether new hires are eligible.</span></span> |
   | <span data-ttu-id="9e41e-134">**Period för ny anställningsanmälan**</span><span class="sxs-lookup"><span data-stu-id="9e41e-134">**New hire enrollment period**</span></span> | <span data-ttu-id="9e41e-135">Den tidsperiod då den nya anställningsanmälan är tillåten.</span><span class="sxs-lookup"><span data-stu-id="9e41e-135">The period of time the new hire enrollment is allowed.</span></span></br></br><span data-ttu-id="9e41e-136">**Obs**! den här inställningen åsidosätter eventuella nya anställningsperioder för anställningsanmälan som du ställer in i berättiganderegler för planen.</span><span class="sxs-lookup"><span data-stu-id="9e41e-136">**Note**: This setting overrides any new hire enrollment period you set on the plan eligibility rule.</span></span> |
   | <span data-ttu-id="9e41e-137">**Standardvärde för lönefrekvens**</span><span class="sxs-lookup"><span data-stu-id="9e41e-137">**Default pay frequency**</span></span> | <span data-ttu-id="9e41e-138">Standard lönefrekvensen som används när nya arbetare läggs till.</span><span class="sxs-lookup"><span data-stu-id="9e41e-138">The default pay frequency to use when new workers are added.</span></span> |
   | <span data-ttu-id="9e41e-139">**Livshändelser har aktiverats**</span><span class="sxs-lookup"><span data-stu-id="9e41e-139">**Life events enabled**</span></span> | <span data-ttu-id="9e41e-140">Aktiverar livshändelser.</span><span class="sxs-lookup"><span data-stu-id="9e41e-140">Enables life events.</span></span> |
   | <span data-ttu-id="9e41e-141">**Dölj formulären för tidigare förmåner**</span><span class="sxs-lookup"><span data-stu-id="9e41e-141">**Hide legacy benefit forms**</span></span> | <span data-ttu-id="9e41e-142">Gör att du kan dölja äldre förmånsformulär.</span><span class="sxs-lookup"><span data-stu-id="9e41e-142">Allows you to hide legacy benefit forms.</span></span> |

3. <span data-ttu-id="9e41e-143">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="9e41e-143">Select **Save**.</span></span>

## <a name="configure-employee-self-service-parameters"></a><span data-ttu-id="9e41e-144">Konfigurera anställdas självbetjäningsparametrar</span><span class="sxs-lookup"><span data-stu-id="9e41e-144">Configure Employee self service parameters</span></span>

1. <span data-ttu-id="9e41e-145">I arbetsytan **Förmånshantering** under **inställningar**, välj **Personalparametrar**.</span><span class="sxs-lookup"><span data-stu-id="9e41e-145">In the **Benefits management** workspace, under **Setup**, select **Human Resources Parameters**.</span></span>

2. <span data-ttu-id="9e41e-146">På fliken **Självbetjäning för medarbetare** ange värden för följande fält:</span><span class="sxs-lookup"><span data-stu-id="9e41e-146">In the **Employee self service** tab, specify values for the following fields:</span></span>

   | <span data-ttu-id="9e41e-147">Fält</span><span class="sxs-lookup"><span data-stu-id="9e41e-147">Field</span></span> | <span data-ttu-id="9e41e-148">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="9e41e-148">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="9e41e-149">**Förmånsverifiering**</span><span class="sxs-lookup"><span data-stu-id="9e41e-149">**Benefit verification**</span></span> | <span data-ttu-id="9e41e-150">Verifieringstext under utcheckningen från självbetjäningen för förmåner.</span><span class="sxs-lookup"><span data-stu-id="9e41e-150">The verification text to use during self-service benefits checkout.</span></span> |
   | <span data-ttu-id="9e41e-151">**Välj befullmäktigade automatiskt**</span><span class="sxs-lookup"><span data-stu-id="9e41e-151">**Auto select designees**</span></span> | <span data-ttu-id="9e41e-152">Anger om man automatiskt ska välja beroende och stödmottagare baserat på deras berättigande till planalternativ.</span><span class="sxs-lookup"><span data-stu-id="9e41e-152">Specifies whether to automatically select dependents and beneficiaries based on their eligibility for plan options.</span></span> |

3. <span data-ttu-id="9e41e-153">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="9e41e-153">Select **Save**.</span></span>
