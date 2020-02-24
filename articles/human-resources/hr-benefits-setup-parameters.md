---
title: Ställ in parametrar för hantering av förmåner
description: Konfigurera parametrar för förmånshantering i Microsoft Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
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
ms.openlocfilehash: ab9b1fc78ce42479d9265b80337adf899cec3866
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010607"
---
# <a name="set-benefits-management-parameters"></a><span data-ttu-id="1d9e9-103">Ställ in parametrar för hantering av förmåner</span><span class="sxs-lookup"><span data-stu-id="1d9e9-103">Set Benefits management parameters</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="1d9e9-104">Innan du kan ställa in tjänstledighetsplaner i Microsoft Dynamics 365 Human Resources måste du konfigurera parametrar för hantering av förmåner.</span><span class="sxs-lookup"><span data-stu-id="1d9e9-104">Before you can set up leave plans in Microsoft Dynamics 365 Human Resources, you need to configure Benefits management parameters.</span></span> <span data-ttu-id="1d9e9-105">Dessa parametrar ställer in standardvärden, orsakskoder och andra alternativ.</span><span class="sxs-lookup"><span data-stu-id="1d9e9-105">These parameters set default values, reason codes, and other options.</span></span>

## <a name="configure-general-parameters"></a><span data-ttu-id="1d9e9-106">Konfigurera allmänna parametrar</span><span class="sxs-lookup"><span data-stu-id="1d9e9-106">Configure general parameters</span></span>

1. <span data-ttu-id="1d9e9-107">I arbetsytan **Förmånshantering** under **inställningar**, välj **parametrar**.</span><span class="sxs-lookup"><span data-stu-id="1d9e9-107">In the **Benefits management** workspace, under **Setup**, select **Parameters**.</span></span>

2. <span data-ttu-id="1d9e9-108">På fliken **Allmänt**, ange värden för följande fält:</span><span class="sxs-lookup"><span data-stu-id="1d9e9-108">In the **General** tab, specify values for the following fields:</span></span>

   | <span data-ttu-id="1d9e9-109">Fält</span><span class="sxs-lookup"><span data-stu-id="1d9e9-109">Field</span></span> | <span data-ttu-id="1d9e9-110">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="1d9e9-110">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="1d9e9-111">**Land/region**</span><span class="sxs-lookup"><span data-stu-id="1d9e9-111">**Country/region**</span></span> | <span data-ttu-id="1d9e9-112">Fältet **land/region** bestämmer visningsordningen för postnummer och stater.</span><span class="sxs-lookup"><span data-stu-id="1d9e9-112">The **Country/region** field determines the display order of ZIP codes/states.</span></span> <span data-ttu-id="1d9e9-113">Det valda landet visas först i den nedrullningsbara listan.</span><span class="sxs-lookup"><span data-stu-id="1d9e9-113">The selected country displays first in the dropdown list.</span></span> |
   | <span data-ttu-id="1d9e9-114">**Orsakskod för anmälan**</span><span class="sxs-lookup"><span data-stu-id="1d9e9-114">**Enrollment reason code**</span></span> | <span data-ttu-id="1d9e9-115">Välj en standardorsakskod som ska användas när medarbetares planer skapas när du öppnar registreringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="1d9e9-115">Select a default reason code to use when employee plans are created during open enrollment processing.</span></span> |
   | <span data-ttu-id="1d9e9-116">**Orsakskod för annullering**</span><span class="sxs-lookup"><span data-stu-id="1d9e9-116">**Cancellation reason code**</span></span> | <span data-ttu-id="1d9e9-117">Orsakskoden som ska användas när en förmånsplanen för medarbetare annulleras.</span><span class="sxs-lookup"><span data-stu-id="1d9e9-117">The reason code to use when an employee benefit plan is canceled.</span></span> <span data-ttu-id="1d9e9-118">Den visas i en dialogruta under annulleringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="1d9e9-118">It displays in a dialog during the cancellation process.</span></span> <span data-ttu-id="1d9e9-119">Användare kan ändra **Orsakskod för annullering** vid behov.</span><span class="sxs-lookup"><span data-stu-id="1d9e9-119">Users can change it the **Cancellation reason code** if necessary.</span></span> |
   | <span data-ttu-id="1d9e9-120">**Öppna orsakskod igen**</span><span class="sxs-lookup"><span data-stu-id="1d9e9-120">**Reopen reason code**</span></span> | <span data-ttu-id="1d9e9-121">Orsakskoden som ska användas när en förmånsplanen för medarbetare öppnas igen.</span><span class="sxs-lookup"><span data-stu-id="1d9e9-121">The reason code to use when an employee benefit plan is reopened.</span></span> <span data-ttu-id="1d9e9-122">Den visas i en dialogruta under annulleringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="1d9e9-122">It displays in a dialog during the cancellation process.</span></span> <span data-ttu-id="1d9e9-123">Användare kan ändra **Orsakskod för öppnas igen** vid behov.</span><span class="sxs-lookup"><span data-stu-id="1d9e9-123">Users can change the **Reopen reason code** if necessary.</span></span> | 
   | <span data-ttu-id="1d9e9-124">**Orsakskod för livshändelse**</span><span class="sxs-lookup"><span data-stu-id="1d9e9-124">**Life event reason code**</span></span> | <span data-ttu-id="1d9e9-125">Orsakskoden som ska användas när en livshändelse inträffar.</span><span class="sxs-lookup"><span data-stu-id="1d9e9-125">The reason code to use when a life event occurs.</span></span> |
   | <span data-ttu-id="1d9e9-126">**Orsakskod för prisändring**</span><span class="sxs-lookup"><span data-stu-id="1d9e9-126">**Rate change reason code**</span></span> | <span data-ttu-id="1d9e9-127">Orsakskoden som ska användas vid annullering och öppnande av en förmånsplan för medarbetare under uppdateringsprocessen av prisändringen.</span><span class="sxs-lookup"><span data-stu-id="1d9e9-127">The reason code to use when canceling and reopening an employee benefit plan during the rate change update process.</span></span> <span data-ttu-id="1d9e9-128">Den visar vilka poster som ändrades under uppdatering av prisändring.</span><span class="sxs-lookup"><span data-stu-id="1d9e9-128">It indicates which records were changed by the rate change update process.</span></span> |
   | <span data-ttu-id="1d9e9-129">**Berättigad till nyanställning**</span><span class="sxs-lookup"><span data-stu-id="1d9e9-129">**New hire eligible**</span></span> | <span data-ttu-id="1d9e9-130">Anger om nya anställningar är berättigade.</span><span class="sxs-lookup"><span data-stu-id="1d9e9-130">Specifies whether new hires are eligible.</span></span> |
   | <span data-ttu-id="1d9e9-131">**Period för ny anställningsanmälan**</span><span class="sxs-lookup"><span data-stu-id="1d9e9-131">**New hire enrollment period**</span></span> | <span data-ttu-id="1d9e9-132">Den tidsperiod då den nya anställningsanmälan är tillåten.</span><span class="sxs-lookup"><span data-stu-id="1d9e9-132">The period of time the new hire enrollment is allowed.</span></span></br></br><span data-ttu-id="1d9e9-133">**Obs**! den här inställningen åsidosätter eventuella nya anställningsperioder för anställningsanmälan som du ställer in i berättiganderegler för planen.</span><span class="sxs-lookup"><span data-stu-id="1d9e9-133">**Note**: This setting overrides any new hire enrollment period you set on the plan eligibility rule.</span></span> | 
   | <span data-ttu-id="1d9e9-134">**Årlig löneökning**</span><span class="sxs-lookup"><span data-stu-id="1d9e9-134">**Annual salary enhancement**</span></span> | <span data-ttu-id="1d9e9-135">Anger om man automatiskt ska beräkna beloppet för **Årlig inkomst av förmåner** i **Information om anställningsförmånen**.</span><span class="sxs-lookup"><span data-stu-id="1d9e9-135">Specifies whether to automatically calculate the **Annual benefit salary** amount in **Employment Benefit Details**.</span></span> <span data-ttu-id="1d9e9-136">Den är baserad på medarbetarens **lönesats för fast kompensation**, **genomsnittliga timmar** och **lönefrekvens**.</span><span class="sxs-lookup"><span data-stu-id="1d9e9-136">It's based on the employee’s **Fixed compensation pay rate**, **Average hours**, and **Payment frequency**.</span></span></br></br><span data-ttu-id="1d9e9-137">**Genomsnittliga timmar** x **fast lönesats** x **lönefrekvens** (# av löneperioder) = **Årlig inkomst av förmåner**</span><span class="sxs-lookup"><span data-stu-id="1d9e9-137">**Average hours** x **Fixed pay rate** x **Payment frequency** (# of pay periods) = **Annual benefit salary**</span></span> </br></br><span data-ttu-id="1d9e9-138">Om något värde i fälten **Genomsnittliga timmar**, **Fast lönesats** eller **Lönefrekvens** ändras, beräknar systemet automatiskt om anställdas belopp för **Årlig inkomst av förmåner** baserat på de ändrade värdena.</span><span class="sxs-lookup"><span data-stu-id="1d9e9-138">If any of the values in the **Average hours**, **Fixed compensation pay rate**, or **Payment frequency** fields change, the system automatically recalculates the employee’s **Annual benefit salary** amount based on the changed values.</span></span> <span data-ttu-id="1d9e9-139">Systemet skapar en post för **Gäller från** för att identifiera exakt datum och tid för ändringen.</span><span class="sxs-lookup"><span data-stu-id="1d9e9-139">The system creates a **Date effective** record to identify the exact date and time the change occurred.</span></span> <span data-ttu-id="1d9e9-140">Du kan redigera beloppet **Årlig inkomst av förmåner** om det behövs.</span><span class="sxs-lookup"><span data-stu-id="1d9e9-140">You can manually edit the **Annual benefit salary** amount if necessary.</span></span> |
   | <span data-ttu-id="1d9e9-141">**Livshändelser har aktiverats**</span><span class="sxs-lookup"><span data-stu-id="1d9e9-141">**Life events enabled**</span></span> | <span data-ttu-id="1d9e9-142">Aktiverar livshändelser.</span><span class="sxs-lookup"><span data-stu-id="1d9e9-142">Enables life events.</span></span> |
   | <span data-ttu-id="1d9e9-143">**Dölj formulären för tidigare förmåner**</span><span class="sxs-lookup"><span data-stu-id="1d9e9-143">**Hide legacy benefit forms**</span></span> | <span data-ttu-id="1d9e9-144">Gör att du kan dölja äldre förmånsformulär.</span><span class="sxs-lookup"><span data-stu-id="1d9e9-144">Allows you to hide legacy benefit forms.</span></span> |

3. <span data-ttu-id="1d9e9-145">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="1d9e9-145">Select **Save**.</span></span>

## <a name="configure-employee-self-service-parameters"></a><span data-ttu-id="1d9e9-146">Konfigurera anställdas självbetjäningsparametrar</span><span class="sxs-lookup"><span data-stu-id="1d9e9-146">Configure Employee self service parameters</span></span>

1. <span data-ttu-id="1d9e9-147">I arbetsytan **Förmånshantering** under **inställningar**, välj **parametrar**.</span><span class="sxs-lookup"><span data-stu-id="1d9e9-147">In the **Benefits management** workspace, under **Setup**, select **Parameters**.</span></span>

2. <span data-ttu-id="1d9e9-148">På fliken **Självbetjäning för medarbetare** ange värden för följande fält:</span><span class="sxs-lookup"><span data-stu-id="1d9e9-148">In the **Employee self service** tab, specify values for the following fields:</span></span>

   | <span data-ttu-id="1d9e9-149">Fält</span><span class="sxs-lookup"><span data-stu-id="1d9e9-149">Field</span></span> | <span data-ttu-id="1d9e9-150">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="1d9e9-150">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="1d9e9-151">**Förmånsverifiering**</span><span class="sxs-lookup"><span data-stu-id="1d9e9-151">**Benefit verification**</span></span> | <span data-ttu-id="1d9e9-152">Verifieringstext under utcheckningen från självbetjäningen för förmåner.</span><span class="sxs-lookup"><span data-stu-id="1d9e9-152">The verification text to use during self-service benefits checkout.</span></span> |
   | <span data-ttu-id="1d9e9-153">**Välj befullmäktigade automatiskt**</span><span class="sxs-lookup"><span data-stu-id="1d9e9-153">**Auto select designees**</span></span> | <span data-ttu-id="1d9e9-154">Anger om man automatiskt ska välja beroende och stödmottagare baserat på deras berättigande till planalternativ.</span><span class="sxs-lookup"><span data-stu-id="1d9e9-154">Specifies whether to automatically select dependents and beneficiaries based on their eligibility for plan options.</span></span> |

3. <span data-ttu-id="1d9e9-155">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="1d9e9-155">Select **Save**.</span></span>
