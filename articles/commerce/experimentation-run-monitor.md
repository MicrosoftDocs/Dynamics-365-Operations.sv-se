---
title: Köra och övervaka ett experiment
description: I det här avsnittet beskrivs hur du kör och övervakar ett experiment i en tredjepartstjänst. Det beskriver också hur du gör ändringar i varianter efter att experimentet har startats.
author: sushma-rao
manager: AnnBe
ms.date: 10/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 4cb7d863d9d69612aa0c340099c1f7861c9d12ba
ms.sourcegitcommit: b6ab46f6e5ce60e2c3d70a348827eaf60c84cae2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/01/2020
ms.locfileid: "3930291"
---
# <a name="run-and-monitor-an-experiment"></a><span data-ttu-id="fa9ec-104">Köra och övervaka ett experiment</span><span class="sxs-lookup"><span data-stu-id="fa9ec-104">Run and monitor an experiment</span></span>

<span data-ttu-id="fa9ec-105">I det här avsnittet beskrivs hur du kör och övervakar ditt experiment i en annan tillverkare och ändrar varianter om det behövs.</span><span class="sxs-lookup"><span data-stu-id="fa9ec-105">This topic describes how to run and monitor your experiment in a third-party app, and change variations if needed.</span></span> <span data-ttu-id="fa9ec-106">Innan du slutför stegen i det här avsnittet måste du [publicera](experimentation-preview-publish.md) experimentet i Commerce.</span><span class="sxs-lookup"><span data-stu-id="fa9ec-106">Before you complete the steps in this topic, you'll need to [publish](experimentation-preview-publish.md) your experiment in Commerce.</span></span> <span data-ttu-id="fa9ec-107">I bilden nedan visas alla steg som ingår när du ställer in och kör ett experiment på en e-handelswebbplats i Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="fa9ec-107">The following diagram shows all of the steps involved in setting up and running an experiment on an e-Commerce website in Dynamics 365 Commerce.</span></span> <span data-ttu-id="fa9ec-108">Ytterligare steg beskrivs i olika avsnitt.</span><span class="sxs-lookup"><span data-stu-id="fa9ec-108">Additional steps are covered in separate topics.</span></span>

<span data-ttu-id="fa9ec-109">[ ![Experimentets användarresa - kör och övervaka](./media/experimentation_run_monitor.svg) ](./media/experimentation_run_monitor.svg#lightbox)</span><span class="sxs-lookup"><span data-stu-id="fa9ec-109">[ ![Experimentation user journey - Run & Monitor](./media/experimentation_run_monitor.svg) ](./media/experimentation_run_monitor.svg#lightbox)</span></span>

<span data-ttu-id="fa9ec-110">När du har publicerat dina varianter måste du utföra experimentet med alla steg du behöver göra i Commerce.</span><span class="sxs-lookup"><span data-stu-id="fa9ec-110">After you publish your variations, all the steps you need to do in Commerce to run your experiment are done.</span></span> <span data-ttu-id="fa9ec-111">Nästa steg bestämmer vilken variant som ska visas för varje användare när de begär en sida.</span><span class="sxs-lookup"><span data-stu-id="fa9ec-111">The next step is determining which variation to show to each user when they request a page.</span></span> <span data-ttu-id="fa9ec-112">Den tredje partens tjänst gör det enkelt att fastställa, men först måste du aktivera experimentet inom tjänsten.</span><span class="sxs-lookup"><span data-stu-id="fa9ec-112">The third-party service makes that determination, but first you have to activate the experiment within the service.</span></span> <span data-ttu-id="fa9ec-113">Eftersom stegen för att aktivera ett experiment varierar från tjänst till tjänst måste du följa instruktionerna som medföljde tjänsten eller leverantören.</span><span class="sxs-lookup"><span data-stu-id="fa9ec-113">Since the steps for activating an experiment vary from service to service, you'll need to follow the instructions included with your service or provider.</span></span> <span data-ttu-id="fa9ec-114">Om experimentet inte har aktiverats visas standardversionen för sidan utan att några varianter visas.</span><span class="sxs-lookup"><span data-stu-id="fa9ec-114">If the experiment is not activated, users will only see the default version of the page - no variations will be displayed.</span></span>

<span data-ttu-id="fa9ec-115">Du måste hålla experimentet tillräckligt länge för att samla in data för statistiskt giltiga resultat.</span><span class="sxs-lookup"><span data-stu-id="fa9ec-115">You'll need to keep the experiment running long enough to gather data for statistically valid results.</span></span> <span data-ttu-id="fa9ec-116">Använd tjänsten från en annan leverantör för att övervaka de experimentbaserade data och analyser medan experimentet körs.</span><span class="sxs-lookup"><span data-stu-id="fa9ec-116">Use the third-party service to monitor the experiment-related data and analytics while the experiment is running.</span></span>

## <a name="adjust-your-variations"></a><span data-ttu-id="fa9ec-117">Justera varianterna</span><span class="sxs-lookup"><span data-stu-id="fa9ec-117">Adjust your variations</span></span>
<span data-ttu-id="fa9ec-118">Om du av någon anledning skulle behöva ändra varianterna följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="fa9ec-118">If for any reason you need to modify your variations, follow the steps below.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fa9ec-119">Om du gör ändringar i ett publicerat experiment i Commerce eller från tjänsten för tredje part, kan resultaten bli betydligt effektfulla.</span><span class="sxs-lookup"><span data-stu-id="fa9ec-119">If you make changes to a live experiment in Commerce or the third-party service, your results may be significantly impacted.</span></span> <span data-ttu-id="fa9ec-120">Överväg att låta experimentet köra kursen och sedan skapa ett nytt experiment med större ändringar.</span><span class="sxs-lookup"><span data-stu-id="fa9ec-120">Consider letting the experiment run its course and then creating a new experiment for major changes.</span></span>

1. <span data-ttu-id="fa9ec-121">Gå till fliken **experiment** i webbplatsskaparen och välj experimentet.</span><span class="sxs-lookup"><span data-stu-id="fa9ec-121">Go to the **Experiments** tab in site builder and select the experiment.</span></span> 
1. <span data-ttu-id="fa9ec-122">Välj den variant som du vill uppdatera på listrutan.</span><span class="sxs-lookup"><span data-stu-id="fa9ec-122">Select the variation you want to update from the drop-down menu.</span></span>
1. <span data-ttu-id="fa9ec-123">Gör nödvändiga ändringar och förhandsgranska och publicera sedan varianterna.</span><span class="sxs-lookup"><span data-stu-id="fa9ec-123">Make needed changes, then preview and publish the variations.</span></span> <span data-ttu-id="fa9ec-124">Mer information finns i [Förhandsgranska och publicera ett experiment](experimentation-preview-publish.md).</span><span class="sxs-lookup"><span data-stu-id="fa9ec-124">For more information, see [Preview and publish an experiment](experimentation-preview-publish.md).</span></span>
1. <span data-ttu-id="fa9ec-125">Gå till tjänsten från tredje part för att göra eventuella experiment inställningar som är relaterade till ändring.</span><span class="sxs-lookup"><span data-stu-id="fa9ec-125">Go to the third-party service to make any experiment setup-related changes.</span></span>
    
## <a name="previous-step"></a><span data-ttu-id="fa9ec-126">Föregående steg</span><span class="sxs-lookup"><span data-stu-id="fa9ec-126">Previous step</span></span>
[<span data-ttu-id="fa9ec-127">Förhandsgranska och publicera ett experiment</span><span class="sxs-lookup"><span data-stu-id="fa9ec-127">Preview and publish an experiment</span></span>](experimentation-preview-publish.md)

## <a name="next-step"></a><span data-ttu-id="fa9ec-128">Gå vidare</span><span class="sxs-lookup"><span data-stu-id="fa9ec-128">Next step</span></span>
[<span data-ttu-id="fa9ec-129">Höja en variant och slutföra ett experiment</span><span class="sxs-lookup"><span data-stu-id="fa9ec-129">Promote a variation and complete an experiment</span></span>](experimentation-review-complete.md)
