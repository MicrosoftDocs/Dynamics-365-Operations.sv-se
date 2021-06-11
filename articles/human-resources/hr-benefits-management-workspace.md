---
title: Arbetsyta för förmånshantering
description: I detta avsnitt beskrivs funktionen arbetsyta för förmånshantering i Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 02/24/2021
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
ms.search.validFrom: 2020-02-24
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 154c3d70b61869795edc25514e98a28389eeb244
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/18/2021
ms.locfileid: "6052251"
---
# <a name="benefits-management-workspace"></a><span data-ttu-id="2e235-103">Arbetsyta för förmånshantering</span><span class="sxs-lookup"><span data-stu-id="2e235-103">Benefits management workspace</span></span>

[!include [applies to](../includes/applies-to-hr.md)]

[!include [preview feature](./includes/preview-feature.md)]

<span data-ttu-id="2e235-104">I detta avsnitt beskrivs funktionen arbetsyta för **förmånshantering** i Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="2e235-104">This topic describes the **Benefits management** workspace in Dynamics 365 Human Resources.</span></span>

> [!NOTE]
> <span data-ttu-id="2e235-105">Om du vill visa arbetsytan **förmånshantering** måste du först aktivera funktionen för **(förhandsgranska) förmånshantering** i funktionshantering.</span><span class="sxs-lookup"><span data-stu-id="2e235-105">To view the **Benefits management** workspace, you must first enable the **(Preview) Benefits management workspace** feature in Feature management.</span></span> <span data-ttu-id="2e235-106">Mer information om hur du aktiverar förhandsfunktioner finns i [Hantera funktioner](../hr-admin-manage-features.md).</span><span class="sxs-lookup"><span data-stu-id="2e235-106">For more information about enabling preview features, see [Manage features](../hr-admin-manage-features.md).</span></span><br><br><span data-ttu-id="2e235-107">![Aktiver arbetsyta för hantering av förmåner](./media/hr-benefits-management-workspace-enable.png)</span><span class="sxs-lookup"><span data-stu-id="2e235-107">![Enable Benefits management workspace](./media/hr-benefits-management-workspace-enable.png)</span></span>

<span data-ttu-id="2e235-108">Arbetsytan **förmånshantering** ger dig en snabb översikt över fördelar som kräver din uppmärksamhet.</span><span class="sxs-lookup"><span data-stu-id="2e235-108">The **Benefits management** workspace gives you a quick view of benefits items that require your attention.</span></span> <span data-ttu-id="2e235-109">På denna sida kan du se:</span><span class="sxs-lookup"><span data-stu-id="2e235-109">On this page, you can see:</span></span>

- <span data-ttu-id="2e235-110">Summor för artiklar som väntar på åtgärd</span><span class="sxs-lookup"><span data-stu-id="2e235-110">Totals for items awaiting action</span></span>
- <span data-ttu-id="2e235-111">Arbetare med obekräftade val</span><span class="sxs-lookup"><span data-stu-id="2e235-111">Workers with unconfirmed selections</span></span>
- <span data-ttu-id="2e235-112">Arbetare som nyligen registrerade sig till förmåner</span><span class="sxs-lookup"><span data-stu-id="2e235-112">Workers who recently enrolled in benefits</span></span>
- <span data-ttu-id="2e235-113">Arbetare med framtida livshändelser</span><span class="sxs-lookup"><span data-stu-id="2e235-113">Workers with future life events</span></span>
- <span data-ttu-id="2e235-114">Nyanställningar som inte är registrerade</span><span class="sxs-lookup"><span data-stu-id="2e235-114">New hires who aren't enrolled</span></span>
- <span data-ttu-id="2e235-115">Arbetare med aktiva livshändelser</span><span class="sxs-lookup"><span data-stu-id="2e235-115">Workers with active life events</span></span>
- <span data-ttu-id="2e235-116">Arbetare med öppna anmälningar som inte har valt några planer</span><span class="sxs-lookup"><span data-stu-id="2e235-116">Workers with open enrollments who haven't opted for any plans</span></span>

![Arbetsyta för förmånshantering](./media/hr-benefits-management-workspace.png)

## <a name="view-action-items"></a><span data-ttu-id="2e235-118">Visa åtgärdsobjekt</span><span class="sxs-lookup"><span data-stu-id="2e235-118">View action items</span></span>

<span data-ttu-id="2e235-119">Du kan visa åtgärdsobjekten genom att välja en panel eller en flik. Om du väljer en flik kan du visa och välja arbetare direkt på arbetsytan.</span><span class="sxs-lookup"><span data-stu-id="2e235-119">You can view your action items by either selecting a tile or a tab. If you select a tab, you can view and select workers right on the workspace page.</span></span>

![Åtgärdsobjekt](./media/hr-benefits-management-workspace-action-items.png)

<span data-ttu-id="2e235-121">Om du väljer en panel går du till sidan för det området.</span><span class="sxs-lookup"><span data-stu-id="2e235-121">If you select a tile, you go to the page for that area.</span></span> <span data-ttu-id="2e235-122">Om du till exempel väljer någon av dessa visas sidan **Arbetares förmånsplaner** filtrerat för medarbetare som du behöver vidta åtgärder för:</span><span class="sxs-lookup"><span data-stu-id="2e235-122">For example, selecting any of these tiles displays the **Worker benefits plans** page, filtered for employees you need to take action on:</span></span>

- <span data-ttu-id="2e235-123">**Obekräftade val**</span><span class="sxs-lookup"><span data-stu-id="2e235-123">**Unconfirmed selections**</span></span>
- <span data-ttu-id="2e235-124">**Öppna registreringar utan utcheckade planer**</span><span class="sxs-lookup"><span data-stu-id="2e235-124">**Open enrollments with no checked out plans**</span></span>
- <span data-ttu-id="2e235-125">**Registrerad för förmåner**</span><span class="sxs-lookup"><span data-stu-id="2e235-125">**Enrolled in benefits**</span></span>
- <span data-ttu-id="2e235-126">**Nyanställd som inte registrerats**</span><span class="sxs-lookup"><span data-stu-id="2e235-126">**New hire not enrolled**</span></span>

![Förmånsplaner för arbetare](./media/hr-benefits-management-workspace-plans.png)

<span data-ttu-id="2e235-128">Om du väljer panelen **Aktiva livshändelser** eller **Framtida livshändelser** kommer du till en lista över aktiva eller framtida händelser.</span><span class="sxs-lookup"><span data-stu-id="2e235-128">Selecting the **Active life events** or **Future life events** tiles takes you to a list of active or future life events.</span></span>

![Livshändelser](./media/hr-benefits-management-workspace-life-events.png)

## <a name="processing"></a><span data-ttu-id="2e235-130">Bearbetas</span><span class="sxs-lookup"><span data-stu-id="2e235-130">Processing</span></span>

<span data-ttu-id="2e235-131">När du vill bearbeta anmälan, livscykelhändelser eller kursändringsuppdateringar markerar du lämpligt objekt i navigeringsfältet.</span><span class="sxs-lookup"><span data-stu-id="2e235-131">To process enrollment eligibility, life events, or rate change updates, select the appropriate item on the navigation bar.</span></span>

![Bearbetas](./media/hr-benefits-management-workspace-processing.png)

<span data-ttu-id="2e235-133">Om du vill visa processresultaten, välj **Processresultat** på sidan.</span><span class="sxs-lookup"><span data-stu-id="2e235-133">To view process results, select **Process results** on the page.</span></span>

![Processresultat](./media/hr-benefits-management-workspace-process-results.png)

<span data-ttu-id="2e235-135">Mer information om förmånsbearbetning finns i:.</span><span class="sxs-lookup"><span data-stu-id="2e235-135">For more information about benefits processing, see:</span></span>

- [<span data-ttu-id="2e235-136">Bearbeta anmälningsberättigande</span><span class="sxs-lookup"><span data-stu-id="2e235-136">Process enrollment eligibility</span></span>](hr-benefits-process-enrollment-eligibility.md)
- [<span data-ttu-id="2e235-137">Bearbeta ändringar av livshändelser</span><span class="sxs-lookup"><span data-stu-id="2e235-137">Process life event changes</span></span>](hr-benefits-process-life-event-changes.md)
- [<span data-ttu-id="2e235-138">Bearbeta livshändelseberättigande</span><span class="sxs-lookup"><span data-stu-id="2e235-138">Process life event eligibility</span></span>](hr-benefits-process-life-event-eligibility.md)
- [<span data-ttu-id="2e235-139">Bearbeta livshändelser</span><span class="sxs-lookup"><span data-stu-id="2e235-139">Process life events</span></span>](hr-benefits-process-life-events.md)
- [<span data-ttu-id="2e235-140">Bearbeta ändringar av sats</span><span class="sxs-lookup"><span data-stu-id="2e235-140">Process rate changes</span></span>](hr-benefits-process-rate-changes.md)

## <a name="change-period"></a><span data-ttu-id="2e235-141">Ändringsperiod</span><span class="sxs-lookup"><span data-stu-id="2e235-141">Change period</span></span>

<span data-ttu-id="2e235-142">Om du vill visa en annan förmånsperiod väljer du den från listrutan **Period**.</span><span class="sxs-lookup"><span data-stu-id="2e235-142">To view a different benefits period, select it from the **Period** dropdown.</span></span>

![Ändringsperiod](./media/hr-benefits-management-workspace-period.png)

## <a name="view-more-options"></a><span data-ttu-id="2e235-144">Visa fler alternativ</span><span class="sxs-lookup"><span data-stu-id="2e235-144">View more options</span></span>

<span data-ttu-id="2e235-145">Om du vill visa mer information och åtgärder som du kan vidta väljer du **Länkar**.</span><span class="sxs-lookup"><span data-stu-id="2e235-145">To view more information and actions you can take, select **Links**.</span></span>

![Länkar](./media/hr-benefits-management-workspace-links.png)

## <a name="see-also"></a><span data-ttu-id="2e235-147">Se även</span><span class="sxs-lookup"><span data-stu-id="2e235-147">See also</span></span>

[<span data-ttu-id="2e235-148">Hantering av förmåner – översikt</span><span class="sxs-lookup"><span data-stu-id="2e235-148">Benefits management overview</span></span>](hr-benefits-management-overview.md)